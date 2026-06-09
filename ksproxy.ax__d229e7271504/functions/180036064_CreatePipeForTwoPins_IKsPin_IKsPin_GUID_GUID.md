# CreatePipeForTwoPins(IKsPin *,IKsPin *,_GUID,_GUID)

- ea: `0x180036064`
- end: `0x180036328`
- name: `?CreatePipeForTwoPins@@YAHPEAUIKsPin@@0U_GUID@@1@Z`
- size: `708`
- prototype: `_BOOL8 __fastcall(struct IKsPin *, struct IKsPin *, struct _GUID *, struct _GUID *)`
- caller_count: `3`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180033570`
- `0x1800399ac`
- `0x18003aa30`

## callees

- `0x180002b58`
- `0x18000f7e0`
- `0x180018894`
- `0x18002ca70`
- `0x180032cf0`
- `0x180035efc`
- `0x180036064`
- `0x18003824c`
- `0x180038844`
- `0x180045010`

## pseudocode

```c
_BOOL8 __fastcall CreatePipeForTwoPins(struct IKsPin *a1, struct IKsPin *a2, struct _GUID *a3, struct _GUID *a4)
{
  int v9; // ebx
  _ALLOCATOR_PROPERTIES_EX *v10; // rax
  struct _GUID v11; // xmm1
  _ALLOCATOR_PROPERTIES_EX *v12; // rsi
  enum KS_LogicalMemoryType *p_LogicalMemoryType; // rbx
  unsigned int *v14; // [rsp+28h] [rbp-50h]
  IMemAllocator *v15; // [rsp+40h] [rbp-38h] BYREF
  __int64 v16; // [rsp+48h] [rbp-30h] BYREF
  __int64 v17; // [rsp+50h] [rbp-28h] BYREF
  struct _GUID Buf1; // [rsp+60h] [rbp-18h] BYREF
  struct IKsAllocatorEx *v19; // [rsp+B0h] [rbp+38h] BYREF

  v17 = 0;
  v16 = 0;
  v19 = 0;
  v15 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x7Fu, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, a1, a2);
  if ( a1->QueryInterface(a1, &GUID_e539cd90_a8b4_11d1_8189_00a0c9062802, (void **)&v17) < 0 )
  {
    v17 = 0;
    return 0;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  if ( a2->QueryInterface(a2, &GUID_e539cd90_a8b4_11d1_8189_00a0c9062802, (void **)&v16) < 0 )
  {
    v16 = 0;
    return 0;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  v9 = CreatePipe(a2, &v19);
  if ( v9 >= 0 )
  {
    v9 = InitializePipe(v19);
    if ( v9 >= 0 )
    {
      v9 = v19->QueryInterface(v19, &GUID_56a8689c_0ad4_11ce_b03a_0020af0ba770, (void **)&v15);
      if ( v9 >= 0 )
      {
        v15->Release(v15);
        if ( !a2->KsPeekAllocator(a2, 0) )
          a2->KsReceiveAllocator(a2, v15);
        (*(void (__fastcall **)(__int64, struct IKsAllocatorEx *))(*(_QWORD *)v16 + 56LL))(v16, v19);
        if ( !a1->KsPeekAllocator(a1, 0) )
          a1->KsReceiveAllocator(a1, v15);
        (*(void (__fastcall **)(__int64, struct IKsAllocatorEx *))(*(_QWORD *)v17 + 56LL))(v17, v19);
        v10 = v19->KsGetProperties(v19);
        v11 = *a4;
        v12 = v10;
        Buf1 = *a3;
        v10->BusType = Buf1;
        p_LogicalMemoryType = &v10->LogicalMemoryType;
        v10->MemoryType = v11;
        if ( (unsigned int)IsHostSystemBus(&Buf1) )
        {
          Buf1 = *a4;
          GetLogicalMemoryTypeFromMemoryType(&Buf1, 0x20u, p_LogicalMemoryType);
        }
        else
        {
          *p_LogicalMemoryType = KS_MemoryTypeDeviceSpecific;
        }
        Buf1 = *a4;
        v12->NumberPins = 2;
        AssignPipeAllocatorHandler(a1, 4u, &Buf1, 2, 0, v14, 1);
        v9 = ResolvePipeDimensions(a1, 4);
        v19->Release(v19);
      }
      else
      {
        v15 = 0;
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x80u, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, v9);
  return v9 >= 0;
}

```

## disassembly

```asm
0x180036064  push    rbp
0x180036066  push    rbx
0x180036067  push    rsi
0x180036068  push    rdi
0x180036069  push    r14
0x18003606b  push    r15
0x18003606d  mov     rbp, rsp
0x180036070  sub     rsp, 78h
0x180036074  mov     r14, r9
0x180036077  mov     [rbp+var_28], 0
0x18003607f  mov     r15, r8
0x180036082  mov     [rbp+var_30], 0
0x18003608a  mov     rsi, rdx
0x18003608d  mov     [rbp+arg_0], 0
0x180036095  mov     rdi, rcx
0x180036098  mov     [rbp+var_38], 0
0x1800360a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800360a7  lea     rax, WPP_GLOBAL_Control
0x1800360ae  cmp     rcx, rax
0x1800360b1  jz      short loc_1800360D6
0x1800360b3  cmp     byte ptr [rcx+19h], 2
0x1800360b7  jb      short loc_1800360D6
0x1800360b9  mov     rcx, [rcx+10h]
0x1800360bd  lea     r8, WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids
0x1800360c4  mov     edx, 7Fh
0x1800360c9  mov     [rsp+78h+var_58], rsi
0x1800360ce  mov     r9, rdi
0x1800360d1  call    WPP_SF_qq
0x1800360d6  mov     rax, [rdi]
0x1800360d9  lea     r8, [rbp+var_28]
0x1800360dd  lea     rdx, _GUID_e539cd90_a8b4_11d1_8189_00a0c9062802
0x1800360e4  mov     rcx, rdi
0x1800360e7  mov     rax, [rax]
0x1800360ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800360ef  test    eax, eax
0x1800360f1  jns     short loc_1800360FD
0x1800360f3  mov     [rbp+var_28], 0
0x1800360fb  jmp     short loc_180036132
0x1800360fd  mov     rcx, [rbp+var_28]
0x180036101  mov     rax, [rcx]
0x180036104  mov     rax, [rax+10h]
0x180036108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003610d  mov     rax, [rsi]
0x180036110  lea     r8, [rbp+var_30]
0x180036114  lea     rdx, _GUID_e539cd90_a8b4_11d1_8189_00a0c9062802
0x18003611b  mov     rcx, rsi
0x18003611e  mov     rax, [rax]
0x180036121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036126  test    eax, eax
0x180036128  jns     short loc_180036139
0x18003612a  mov     [rbp+var_30], 0
0x180036132  xor     eax, eax
0x180036134  jmp     loc_18003631A
0x180036139  mov     rcx, [rbp+var_30]
0x18003613d  mov     rax, [rcx]
0x180036140  mov     rax, [rax+10h]
0x180036144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036149  lea     rdx, [rbp+arg_0]; struct IKsAllocatorEx **
0x18003614d  mov     rcx, rsi; struct IKsPin *
0x180036150  call    ?CreatePipe@@YAJPEAUIKsPin@@PEAPEAUIKsAllocatorEx@@@Z; CreatePipe(IKsPin *,IKsAllocatorEx * *)
0x180036155  mov     ebx, eax
0x180036157  test    eax, eax
0x180036159  js      loc_1800362E2
0x18003615f  mov     rcx, [rbp+arg_0]; struct IKsAllocatorEx *
0x180036163  call    ?InitializePipe@@YAJPEAUIKsAllocatorEx@@H@Z; InitializePipe(IKsAllocatorEx *,int)
0x180036168  mov     ebx, eax
0x18003616a  test    eax, eax
0x18003616c  js      loc_1800362E2
0x180036172  mov     rcx, [rbp+arg_0]
0x180036176  lea     r8, [rbp+var_38]
0x18003617a  lea     rdx, _GUID_56a8689c_0ad4_11ce_b03a_0020af0ba770
0x180036181  mov     rax, [rcx]
0x180036184  mov     rax, [rax]
0x180036187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003618c  mov     ebx, eax
0x18003618e  test    eax, eax
0x180036190  jns     short loc_18003619F
0x180036192  mov     [rbp+var_38], 0
0x18003619a  jmp     loc_1800362E2
0x18003619f  mov     rcx, [rbp+var_38]
0x1800361a3  mov     rax, [rcx]
0x1800361a6  mov     rax, [rax+10h]
0x1800361aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800361af  mov     rax, [rsi]
0x1800361b2  xor     edx, edx
0x1800361b4  mov     rcx, rsi
0x1800361b7  mov     rax, [rax+50h]
0x1800361bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800361c0  test    rax, rax
0x1800361c3  jnz     short loc_1800361D8
0x1800361c5  mov     rax, [rsi]
0x1800361c8  mov     rcx, rsi
0x1800361cb  mov     rdx, [rbp+var_38]
0x1800361cf  mov     rax, [rax+58h]
0x1800361d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800361d8  mov     rcx, [rbp+var_30]
0x1800361dc  mov     rdx, [rbp+arg_0]
0x1800361e0  mov     rax, [rcx]
0x1800361e3  mov     rax, [rax+38h]
0x1800361e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800361ec  mov     rax, [rdi]
0x1800361ef  xor     edx, edx
0x1800361f1  mov     rcx, rdi
0x1800361f4  mov     rax, [rax+50h]
0x1800361f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800361fd  test    rax, rax
0x180036200  jnz     short loc_180036215
0x180036202  mov     rax, [rdi]
0x180036205  mov     rcx, rdi
0x180036208  mov     rdx, [rbp+var_38]
0x18003620c  mov     rax, [rax+58h]
0x180036210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036215  mov     rcx, [rbp+var_28]
0x180036219  mov     rdx, [rbp+arg_0]
0x18003621d  mov     rax, [rcx]
0x180036220  mov     rax, [rax+38h]
0x180036224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036229  mov     rcx, [rbp+arg_0]
0x18003622d  mov     rax, [rcx]
0x180036230  mov     rax, [rax+38h]
0x180036234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036239  movaps  xmm0, xmmword ptr [r15]
0x18003623d  lea     rcx, [rbp+Buf1]; Buf1
0x180036241  movaps  xmm1, xmmword ptr [r14]
0x180036245  mov     rsi, rax
0x180036248  movdqa  xmmword ptr [rbp+Buf1.Data1], xmm0
0x18003624d  movdqu  xmmword ptr [rax+20h], xmm0
0x180036252  lea     rbx, [rax+0B0h]
0x180036259  movdqu  xmmword ptr [rax+10h], xmm1
0x18003625e  call    ?IsHostSystemBus@@YAHU_GUID@@@Z; IsHostSystemBus(_GUID)
0x180036263  mov     r15d, 4
0x180036269  test    eax, eax
0x18003626b  jnz     short loc_180036272
0x18003626d  mov     [rbx], r15d
0x180036270  jmp     short loc_18003628C
0x180036272  movaps  xmm0, xmmword ptr [r14]
0x180036276  lea     rcx, [rbp+Buf1]; Buf1
0x18003627a  mov     r8, rbx; enum KS_LogicalMemoryType *
0x18003627d  movdqa  xmmword ptr [rbp+Buf1.Data1], xmm0
0x180036282  mov     edx, 20h ; ' '; unsigned int
0x180036287  call    ?GetLogicalMemoryTypeFromMemoryType@@YAHU_GUID@@KPEAW4KS_LogicalMemoryType@@@Z; GetLogicalMemoryTypeFromMemoryType(_GUID,ulong,KS_LogicalMemoryType *)
0x18003628c  movaps  xmm0, xmmword ptr [r14]
0x180036290  lea     r8, [rbp+Buf1]; struct _GUID
0x180036294  mov     [rsp+78h+var_48], 1; int
0x18003629c  mov     r9d, 2; unsigned int
0x1800362a2  mov     edx, r15d; unsigned int
0x1800362a5  movdqa  xmmword ptr [rbp+Buf1.Data1], xmm0
0x1800362aa  mov     rcx, rdi; struct IKsPin *
0x1800362ad  mov     dword ptr [rsi+104h], 2
0x1800362b7  mov     [rsp+78h+var_58], 0; struct IKsPin **
0x1800362c0  call    ?AssignPipeAllocatorHandler@@YAHPEAUIKsPin@@KU_GUID@@KPEAPEAU1@PEAKH@Z; AssignPipeAllocatorHandler(IKsPin *,ulong,_GUID,ulong,IKsPin * *,ulong *,int)
0x1800362c5  mov     edx, r15d; unsigned int
0x1800362c8  mov     rcx, rdi; struct IKsPin *
0x1800362cb  call    ?ResolvePipeDimensions@@YAJPEAUIKsPin@@KK@Z; ResolvePipeDimensions(IKsPin *,ulong,ulong)
0x1800362d0  mov     rcx, [rbp+arg_0]
0x1800362d4  mov     ebx, eax
0x1800362d6  mov     rax, [rcx]
0x1800362d9  mov     rax, [rax+10h]
0x1800362dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800362e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800362e9  lea     rax, WPP_GLOBAL_Control
0x1800362f0  cmp     rcx, rax
0x1800362f3  jz      short loc_180036313
0x1800362f5  cmp     byte ptr [rcx+19h], 2
0x1800362f9  jb      short loc_180036313
0x1800362fb  mov     rcx, [rcx+10h]
0x1800362ff  lea     r8, WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids
0x180036306  mov     edx, 80h
0x18003630b  mov     r9d, ebx
0x18003630e  call    WPP_SF_d
0x180036313  xor     eax, eax
0x180036315  test    ebx, ebx
0x180036317  setns   al
0x18003631a  add     rsp, 78h
0x18003631e  pop     r15
0x180036320  pop     r14
0x180036322  pop     rdi
0x180036323  pop     rsi
0x180036324  pop     rbx
0x180036325  pop     rbp
0x180036326  retn
```
