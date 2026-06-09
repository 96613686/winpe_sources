# RtMgrRoutingDomainConfig::EnableOrDisableProtocol(ulong,ulong,int)

- ea: `0x1800557a0`
- end: `0x1800559d2`
- name: `?EnableOrDisableProtocol@RtMgrRoutingDomainConfig@@QEAAXKKH@Z`
- size: `562`
- prototype: `void __fastcall(struct _GUID *this, unsigned int, unsigned int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800559d8`

## callees

- `0x1800557a0`
- `0x180058068`
- `0x180058124`
- `0x18005852a`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180055820`
- `ntdll!RtlAcquireResourceExclusive` at `0x180055820`
- `ntdll!RtlReleaseResource` at `0x1800559a6`
- `ntdll!RtlReleaseResource` at `0x1800559a6`
- `KERNEL32!HeapFree` at `0x1800558ce`
- `KERNEL32!HeapFree` at `0x180055909`
- `KERNEL32!HeapFree` at `0x180055987`
- `KERNEL32!HeapFree` at `0x1800558ce`
- `KERNEL32!HeapFree` at `0x180055909`
- `KERNEL32!HeapFree` at `0x180055987`
- `KERNEL32!HeapAlloc` at `0x180055899`
- `KERNEL32!HeapAlloc` at `0x180055940`
- `KERNEL32!HeapAlloc` at `0x180055899`
- `KERNEL32!HeapAlloc` at `0x180055940`

## string_xrefs

- `0x1800557ff`: `RtMgrRoutingDomainConfig::EnableOrDisableProtocol`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RtMgrRoutingDomainConfig::EnableOrDisableProtocol(
        struct _GUID *this,
        int a2,
        unsigned int *a3,
        void (*a4)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))
{
  int v4; // r13d
  int v5; // ebp
  int v7; // r12d
  __int64 v8; // r15
  __int64 v9; // rax
  __int64 Data1; // rdi
  __int64 v11; // r14
  __int64 v12; // rax
  _DWORD *v13; // rsi
  __int64 i; // rcx
  _DWORD *v15; // rax
  _DWORD *v16; // r12
  _DWORD *v17; // r14
  __int64 v18; // r8
  __int64 v19; // rdx
  int v20; // eax
  int v21; // r9d
  unsigned __int16 *v22; // [rsp+28h] [rbp-A0h]
  unsigned int v23; // [rsp+30h] [rbp-98h]
  __int64 v24; // [rsp+40h] [rbp-88h]
  __int64 v25; // [rsp+50h] [rbp-78h] BYREF
  __int128 v26; // [rsp+58h] [rbp-70h]
  __int128 v27; // [rsp+68h] [rbp-60h]
  __int64 v28; // [rsp+78h] [rbp-50h]
  int v29; // [rsp+80h] [rbp-48h]
  int v30; // [rsp+84h] [rbp-44h]
  __int64 v31; // [rsp+D0h] [rbp+8h]

  v4 = (int)a4;
  v5 = (int)a3;
  v7 = 0;
  v26 = 0;
  v25 = 0;
  v27 = 0;
  v28 = 0;
  v29 = -1;
  v30 = 0;
  if ( *((_QWORD *)&xmmword_18008B450 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v25,
      L"RtMgrRoutingDomainConfig::EnableOrDisableProtocol",
      a3,
      a4,
      this,
      v22,
      v23);
  RtlAcquireResourceExclusive((PRTL_RESOURCE)&this[42], 1u);
  v8 = 36;
  v9 = 36;
  if ( v5 != 33 )
    v9 = 40;
  v24 = v9 * 16;
  Data1 = this[v9].Data1;
  v11 = 584;
  v12 = 584;
  if ( v5 != 33 )
    v12 = 648;
  v31 = v12;
  v13 = *(_DWORD **)((char *)&this->Data1 + v12);
  for ( i = 0; (unsigned int)i < (unsigned int)Data1; i = (unsigned int)(i + 1) )
  {
    if ( a2 == v13[i] )
    {
      v7 = 1;
      break;
    }
  }
  if ( v7 != v4 )
  {
    if ( v4 )
    {
      v15 = HeapAlloc(IPRouterHeap, 0, 4LL * (unsigned int)(Data1 + 1));
      v16 = v15;
      if ( v15 )
      {
        if ( v13 )
        {
          memcpy_0(v15, v13, 4 * Data1);
          HeapFree(IPRouterHeap, 0, v13);
        }
        v16[Data1] = a2;
        if ( v5 != 33 )
          v11 = 648;
        *(_QWORD *)((char *)&this->Data1 + v11) = v16;
        if ( v5 != 33 )
          v8 = 40;
        this[v8].Data1 = Data1 + 1;
      }
    }
    else if ( (_DWORD)Data1 == 1 )
    {
      HeapFree(IPRouterHeap, 0, *(LPVOID *)((char *)&this->Data1 + v12));
      if ( v5 != 33 )
        v11 = 648;
      *(_QWORD *)((char *)&this->Data1 + v11) = 0;
      if ( v5 != 33 )
        v8 = 40;
      this[v8].Data1 = 0;
    }
    else
    {
      v17 = HeapAlloc(IPRouterHeap, 0, 4LL * (unsigned int)(Data1 - 1));
      if ( v17 )
      {
        v18 = 0;
        v19 = 0;
        if ( (_DWORD)Data1 )
        {
          v20 = a2;
          do
          {
            v21 = v13[v19];
            if ( v21 != v20 )
            {
              v17[v18] = v21;
              v18 = (unsigned int)(v18 + 1);
              v20 = a2;
            }
            v19 = (unsigned int)(v19 + 1);
          }
          while ( (unsigned int)v19 < (unsigned int)Data1 );
        }
        HeapFree(IPRouterHeap, 0, v13);
        *(_QWORD *)((char *)&this->Data1 + v31) = v17;
        *(unsigned int *)((char *)&this->Data1 + v24) = Data1 - 1;
      }
    }
  }
  RtlReleaseResource((PRTL_RESOURCE)&this[42]);
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v25);
}

```

## disassembly

```asm
0x1800557a0  mov     r11, rsp
0x1800557a3  mov     [r11+18h], rbx
0x1800557a7  mov     [rsp+arg_8], edx
0x1800557ab  push    rbp
0x1800557ac  push    rsi
0x1800557ad  push    rdi
0x1800557ae  push    r12
0x1800557b0  push    r13
0x1800557b2  push    r14
0x1800557b4  push    r15
0x1800557b6  sub     rsp, 90h
0x1800557bd  mov     r13d, r9d
0x1800557c0  mov     ebp, r8d
0x1800557c3  mov     rbx, rcx
0x1800557c6  xor     eax, eax
0x1800557c8  mov     r12d, eax
0x1800557cb  xorps   xmm0, xmm0
0x1800557ce  movdqu  [rsp+0C8h+var_70], xmm0
0x1800557d4  mov     [r11-78h], rax
0x1800557d8  xorps   xmm1, xmm1
0x1800557db  movdqu  [rsp+0C8h+var_60], xmm1
0x1800557e1  mov     [r11-50h], rax
0x1800557e5  mov     dword ptr [r11-48h], 0FFFFFFFFh
0x1800557ed  mov     [r11-44h], eax
0x1800557f1  cmp     qword ptr cs:xmmword_18008B450+8, rax
0x1800557f8  jz      short loc_18005580F
0x1800557fa  mov     [rsp+0C8h+var_A8], rcx; struct _GUID *
0x1800557ff  lea     rdx, aRtmgrroutingdo_7; "RtMgrRoutingDomainConfig::EnableOrDisab"...
0x180055806  lea     rcx, [r11-78h]; this
0x18005580a  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18005580f  lea     rax, [rbx+2A0h]
0x180055816  mov     [rsp+0C8h+Resource], rax
0x18005581b  mov     dl, 1; Wait
0x18005581d  mov     rcx, rax; Resource
0x180055820  call    cs:__imp_RtlAcquireResourceExclusive
0x180055826  mov     r15d, 240h
0x18005582c  mov     eax, r15d
0x18005582f  lea     ecx, [r15+40h]
0x180055833  cmp     ebp, 21h ; '!'
0x180055836  cmovnz  eax, ecx
0x180055839  mov     [rsp+0C8h+var_88], rax
0x18005583e  mov     edi, [rax+rbx]
0x180055841  lea     r14d, [r15+8]
0x180055845  mov     eax, r14d
0x180055848  lea     ecx, [r15+48h]
0x18005584c  cmovnz  eax, ecx
0x18005584f  mov     [rsp+0C8h+arg_0], rax
0x180055857  mov     rsi, [rax+rbx]
0x18005585b  xor     ecx, ecx
0x18005585d  mov     edx, [rsp+0C8h+arg_8]
0x180055864  cmp     ecx, edi
0x180055866  jnb     short loc_180055877
0x180055868  cmp     edx, [rsi+rcx*4]
0x18005586b  jz      short loc_180055871
0x18005586d  inc     ecx
0x18005586f  jmp     short loc_180055864
0x180055871  mov     r12d, 1
0x180055877  cmp     r12d, r13d
0x18005587a  jz      loc_1800559A1
0x180055880  xor     edx, edx; dwFlags
0x180055882  mov     rcx, cs:?IPRouterHeap@@3PEAXEA; hHeap
0x180055889  test    r13d, r13d
0x18005588c  jz      short loc_180055901
0x18005588e  lea     r13d, [rdi+1]
0x180055892  mov     r8d, r13d
0x180055895  shl     r8, 2; dwBytes
0x180055899  call    cs:__imp_HeapAlloc
0x18005589f  mov     r12, rax
0x1800558a2  test    rax, rax
0x1800558a5  jz      loc_1800559A1
0x1800558ab  test    rsi, rsi
0x1800558ae  jz      short loc_1800558D4
0x1800558b0  mov     r8, rdi
0x1800558b3  shl     r8, 2; Size
0x1800558b7  mov     rdx, rsi; Src
0x1800558ba  mov     rcx, rax; void *
0x1800558bd  call    memcpy_0
0x1800558c2  mov     r8, rsi; lpMem
0x1800558c5  xor     edx, edx; dwFlags
0x1800558c7  mov     rcx, cs:?IPRouterHeap@@3PEAXEA; hHeap
0x1800558ce  call    cs:__imp_HeapFree
0x1800558d4  mov     ecx, [rsp+0C8h+arg_8]
0x1800558db  mov     [r12+rdi*4], ecx
0x1800558df  cmp     ebp, 21h ; '!'
0x1800558e2  mov     eax, 288h
0x1800558e7  cmovnz  r14, rax
0x1800558eb  mov     [r14+rbx], r12
0x1800558ef  mov     eax, 280h
0x1800558f4  cmovnz  r15, rax
0x1800558f8  mov     [r15+rbx], r13d
0x1800558fc  jmp     loc_1800559A1
0x180055901  cmp     edi, 1
0x180055904  jnz     short loc_180055936
0x180055906  mov     r8, rsi; lpMem
0x180055909  call    cs:__imp_HeapFree
0x18005590f  cmp     ebp, 21h ; '!'
0x180055912  mov     eax, 288h
0x180055917  cmovnz  r14, rax
0x18005591b  mov     qword ptr [r14+rbx], 0
0x180055923  mov     eax, 280h
0x180055928  cmovnz  r15, rax
0x18005592c  mov     dword ptr [r15+rbx], 0
0x180055934  jmp     short loc_1800559A1
0x180055936  lea     ebp, [rdi-1]
0x180055939  mov     r8d, ebp
0x18005593c  shl     r8, 2; dwBytes
0x180055940  call    cs:__imp_HeapAlloc
0x180055946  mov     r14, rax
0x180055949  test    rax, rax
0x18005594c  jz      short loc_1800559A1
0x18005594e  xor     r8d, r8d
0x180055951  xor     edx, edx
0x180055953  test    edi, edi
0x180055955  jz      short loc_18005597B
0x180055957  mov     eax, [rsp+0C8h+arg_8]
0x18005595e  mov     r9d, [rsi+rdx*4]
0x180055962  cmp     r9d, eax
0x180055965  jz      short loc_180055975
0x180055967  mov     [r14+r8*4], r9d
0x18005596b  inc     r8d
0x18005596e  mov     eax, [rsp+0C8h+arg_8]
0x180055975  inc     edx
0x180055977  cmp     edx, edi
0x180055979  jb      short loc_18005595E
0x18005597b  mov     r8, rsi; lpMem
0x18005597e  xor     edx, edx; dwFlags
0x180055980  mov     rcx, cs:?IPRouterHeap@@3PEAXEA; hHeap
0x180055987  call    cs:__imp_HeapFree
0x18005598d  mov     rax, [rsp+0C8h+arg_0]
0x180055995  mov     [rax+rbx], r14
0x180055999  mov     rax, [rsp+0C8h+var_88]
0x18005599e  mov     [rax+rbx], ebp
0x1800559a1  mov     rcx, [rsp+0C8h+Resource]; Resource
0x1800559a6  call    cs:__imp_RtlReleaseResource
0x1800559ac  nop
0x1800559ad  lea     rcx, [rsp+0C8h+var_78]; this
0x1800559b2  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800559b7  mov     rbx, [rsp+0C8h+arg_10]
0x1800559bf  add     rsp, 90h
0x1800559c6  pop     r15
0x1800559c8  pop     r14
0x1800559ca  pop     r13
0x1800559cc  pop     r12
0x1800559ce  pop     rdi
0x1800559cf  pop     rsi
0x1800559d0  pop     rbp
0x1800559d1  retn
```
