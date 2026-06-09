# ACpReceiveMessage

- ea: `0x1400096b0`
- end: `0x14000982c`
- name: `ACpReceiveMessage`
- size: `380`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, __int64, __int64, const struct CQueueBase *, int, unsigned int, unsigned int, __int64, char, __int64, __int64)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x1400047fc`
- `0x1400082ec`
- `0x1400083b8`
- `0x140008478`
- `0x140008534`

## callees

- `0x1400096b0`
- `0x14000b5d8`
- `0x14000cb4c`
- `0x14001a564`
- `0x140024bf0`

## pseudocode

```c
__int64 __fastcall ACpReceiveMessage(
        struct _DEVICE_OBJECT *a1,
        __int64 a2,
        __int64 a3,
        const struct CQueueBase *a4,
        int a5,
        unsigned int a6,
        unsigned int a7,
        __int64 a8,
        char a9,
        __int64 a10,
        __int64 a11)
{
  int v15; // ebx
  int v17; // eax
  __int64 v18; // r8
  char v19; // r10
  struct CCursor *v20; // rax
  struct CCursor *v21; // r9

  v15 = CQueueBase::Validate(a4);
  if ( v15 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_Dq(
        WPP_GLOBAL_Control->Queue.ListEntry.Blink,
        75,
        WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids,
        (unsigned int)v15,
        a4);
    }
    return (unsigned int)v15;
  }
  if ( !*(_BYTE *)(a3 + 76) && (!a5 || a5 == 1073742112 || (a5 & 0x40000020) == 0x40000020)
    || (*(_DWORD *)(*(_QWORD *)(a3 + 32) + 20LL) & 8) != 0 )
  {
    return 3221225506LL;
  }
  v17 = (*(__int64 (__fastcall **)(const struct CQueueBase *))(*(_QWORD *)a4 + 32LL))(a4);
  v18 = a8;
  if ( v17 )
  {
    if ( !a8 )
      goto LABEL_19;
    if ( (*((_DWORD *)a4 + 14) & 2) == 0 )
      return 3222143056LL;
  }
  if ( a8 && (a5 < 0 || (a5 & 0x40000010) == 0x40000010) )
    return 3222143056LL;
LABEL_19:
  v19 = a9;
  if ( a7 )
  {
    v20 = CCursor::Validate(a1, a7);
    v21 = v20;
    if ( !v20 || *((_QWORD *)v20 + 6) != a3 )
      return 3221225480LL;
  }
  else
  {
    v21 = 0;
    if ( (a5 & 0x7FFFFFFF) != 0 && !a9 )
      return 3221225485LL;
  }
  return (*(__int64 (__fastcall **)(const struct CQueueBase *, __int64, _QWORD, struct CCursor *, int, char, __int64, __int64, __int64))(*(_QWORD *)a4 + 8LL))(
           a4,
           a2,
           a6,
           v21,
           a5,
           v19,
           a10,
           v18,
           a11);
}

```

## disassembly

```asm
0x1400096b0  push    rbx
0x1400096b2  push    rbp
0x1400096b3  push    rsi
0x1400096b4  push    rdi
0x1400096b5  push    r14
0x1400096b7  sub     rsp, 50h
0x1400096bb  mov     rbp, rcx
0x1400096be  mov     rdi, r9
0x1400096c1  mov     rcx, r9; struct CQueueBase *
0x1400096c4  mov     rsi, r8
0x1400096c7  mov     r14, rdx
0x1400096ca  call    ?Validate@CQueueBase@@SAJPEBV1@@Z; CQueueBase::Validate(CQueueBase const *)
0x1400096cf  mov     ebx, eax
0x1400096d1  test    eax, eax
0x1400096d3  jns     short loc_140009714
0x1400096d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400096dc  lea     rax, WPP_GLOBAL_Control
0x1400096e3  cmp     rcx, rax
0x1400096e6  jz      short loc_14000970D
0x1400096e8  mov     edx, [rcx+6Ch]
0x1400096eb  test    dl, 1
0x1400096ee  jz      short loc_14000970D
0x1400096f0  mov     rcx, [rcx+58h]
0x1400096f4  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x1400096fb  mov     edx, 4Bh ; 'K'
0x140009700  mov     [rsp+78h+var_58], rdi
0x140009705  mov     r9d, ebx
0x140009708  call    WPP_SF_Dq
0x14000970d  mov     eax, ebx
0x14000970f  jmp     loc_140009820
0x140009714  cmp     byte ptr [rsi+4Ch], 0
0x140009718  mov     ebx, [rsp+78h+arg_20]
0x14000971f  jnz     short loc_14000973A
0x140009721  test    ebx, ebx
0x140009723  jz      short loc_140009746
0x140009725  cmp     ebx, 40000120h
0x14000972b  jz      short loc_140009746
0x14000972d  mov     ecx, 40000020h
0x140009732  mov     eax, ebx
0x140009734  and     eax, ecx
0x140009736  cmp     eax, ecx
0x140009738  jz      short loc_140009746
0x14000973a  mov     rax, [rsi+20h]
0x14000973e  mov     ecx, [rax+14h]
0x140009741  test    cl, 8
0x140009744  jz      short loc_140009750
0x140009746  mov     eax, 0C0000022h
0x14000974b  jmp     loc_140009820
0x140009750  mov     rax, [rdi]
0x140009753  mov     rcx, rdi
0x140009756  mov     rax, [rax+20h]
0x14000975a  call    _guard_dispatch_icall
0x14000975f  mov     r8, [rsp+78h+arg_38]
0x140009767  test    eax, eax
0x140009769  jz      short loc_140009777
0x14000976b  test    r8, r8
0x14000976e  jz      short loc_140009797
0x140009770  mov     eax, [rdi+38h]
0x140009773  test    al, 2
0x140009775  jz      short loc_14000978D
0x140009777  test    r8, r8
0x14000977a  jz      short loc_140009797
0x14000977c  test    ebx, ebx
0x14000977e  js      short loc_14000978D
0x140009780  mov     ecx, 40000010h
0x140009785  mov     eax, ebx
0x140009787  and     eax, ecx
0x140009789  cmp     eax, ecx
0x14000978b  jnz     short loc_140009797
0x14000978d  mov     eax, 0C00E0050h
0x140009792  jmp     loc_140009820
0x140009797  mov     edx, [rsp+78h+arg_30]; unsigned int
0x14000979e  mov     r10b, [rsp+78h+arg_40]
0x1400097a6  test    edx, edx
0x1400097a8  jz      short loc_1400097C7
0x1400097aa  mov     rcx, rbp; struct _DEVICE_OBJECT *
0x1400097ad  call    ?Validate@CCursor@@SAPEAV1@PEAU_DEVICE_OBJECT@@K@Z; CCursor::Validate(_DEVICE_OBJECT *,ulong)
0x1400097b2  mov     r9, rax
0x1400097b5  test    rax, rax
0x1400097b8  jz      short loc_1400097C0
0x1400097ba  cmp     [rax+30h], rsi
0x1400097be  jz      short loc_1400097DE
0x1400097c0  mov     eax, 0C0000008h
0x1400097c5  jmp     short loc_140009820
0x1400097c7  xor     r9d, r9d
0x1400097ca  test    ebx, 7FFFFFFFh
0x1400097d0  jz      short loc_1400097DE
0x1400097d2  test    r10b, r10b
0x1400097d5  jnz     short loc_1400097DE
0x1400097d7  mov     eax, 0C000000Dh
0x1400097dc  jmp     short loc_140009820
0x1400097de  mov     rcx, [rsp+78h+arg_50]
0x1400097e6  mov     rdx, r14
0x1400097e9  mov     rax, [rdi]
0x1400097ec  mov     [rsp+78h+var_38], rcx
0x1400097f1  mov     rcx, [rsp+78h+arg_48]
0x1400097f9  mov     [rsp+78h+var_40], r8
0x1400097fe  mov     rax, [rax+8]
0x140009802  mov     r8d, [rsp+78h+arg_28]
0x14000980a  mov     [rsp+78h+var_48], rcx
0x14000980f  mov     rcx, rdi
0x140009812  mov     [rsp+78h+var_50], r10b
0x140009817  mov     dword ptr [rsp+78h+var_58], ebx
0x14000981b  call    _guard_dispatch_icall
0x140009820  add     rsp, 50h
0x140009824  pop     r14
0x140009826  pop     rdi
0x140009827  pop     rsi
0x140009828  pop     rbp
0x140009829  pop     rbx
0x14000982a  retn
```
