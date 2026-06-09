# CAepStoreAccess::GetProperties(ushort const *,ulong,ulong,_DEVPROPCOMPKEY const *,ulong *,_DEVPROPERTY const * *)

- ea: `0x1400195e0`
- end: `0x140019758`
- name: `?GetProperties@CAepStoreAccess@@UEAAJPEBGKKPEBU_DEVPROPCOMPKEY@@PEAKPEAPEBU_DEVPROPERTY@@@Z`
- size: `376`
- prototype: `__int64 __fastcall(CAepStoreAccess *this, unsigned __int16 *, __int64, __int64, const struct _DEVPROPCOMPKEY *, unsigned int *, const struct _DEVPROPERTY **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140001570`
- `0x140009090`
- `0x1400195e0`
- `0x140019940`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140019722`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140019722`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400196bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400196bd`
- `api-ms-win-devices-query-l1-1-1!DevGetObjectPropertiesEx` at `0x14001970f`
- `api-ms-win-devices-query-l1-1-1!DevGetObjectPropertiesEx` at `0x14001970f`

## pseudocode

```c
__int64 __fastcall CAepStoreAccess::GetProperties(
        CAepStoreAccess *this,
        unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        const struct _DEVPROPCOMPKEY *a5,
        unsigned int *a6,
        const struct _DEVPROPERTY **a7)
{
  __int64 v8; // rdx
  __int64 v10; // rcx
  unsigned __int16 *v11; // rcx
  int AepId; // ebx
  char v14; // [rsp+50h] [rbp-71h] BYREF
  void *v15; // [rsp+58h] [rbp-69h]
  const struct _DEVPROPERTY **v16; // [rsp+60h] [rbp-61h]
  __int128 v17; // [rsp+70h] [rbp-51h]
  int v18; // [rsp+80h] [rbp-41h]
  int v19; // [rsp+84h] [rbp-3Dh]
  int v20; // [rsp+88h] [rbp-39h]
  __int64 v21; // [rsp+90h] [rbp-31h]
  __int64 v22; // [rsp+98h] [rbp-29h]
  unsigned __int64 v23; // [rsp+A0h] [rbp-21h]
  int v24; // [rsp+A8h] [rbp-19h]
  int v25; // [rsp+ACh] [rbp-15h]
  int v26; // [rsp+B0h] [rbp-11h]
  char *v27; // [rsp+B8h] [rbp-9h]

  v8 = -1;
  v16 = a7;
  v10 = *((_QWORD *)this + 2);
  v15 = 0;
  v14 = -1;
  v17 = DEVPKEY_DasParam_PerUserSid;
  v18 = 8;
  v19 = 18;
  if ( v10 )
  {
    do
      ++v8;
    while ( *(_WORD *)(v10 + 2 * v8) );
    v20 = 2 * v8 + 2;
  }
  else
  {
    v20 = 0;
  }
  v22 = DEVPKEY_DasParam_AepStoreOnly;
  v24 = 4;
  v21 = v10;
  v11 = (unsigned __int16 *)*((_QWORD *)this + 3);
  v27 = &v14;
  v23 = 0xBD707D321F829594uLL;
  v25 = 17;
  v26 = 1;
  AepId = DafMakeAepId(v11, a2);
  if ( AepId >= 0 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    if ( *((_DWORD *)this + 8) )
      AepId = DevGetObjectPropertiesEx(5, v15);
    else
      AepId = -2140930029;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  }
  if ( v15 )
    MIDL_user_free(v15);
  return (unsigned int)AepId;
}

```

## disassembly

```asm
0x1400195e0  push    rbp
0x1400195e2  push    rbx
0x1400195e3  push    rsi
0x1400195e4  push    r12
0x1400195e6  push    r13
0x1400195e8  push    r14
0x1400195ea  push    r15
0x1400195ec  lea     rbp, [rsp-0Fh]
0x1400195f1  sub     rsp, 0D0h
0x1400195f8  mov     rax, cs:__security_cookie
0x1400195ff  xor     rax, rsp
0x140019602  mov     [rbp+3Fh+var_40], rax
0x140019606  mov     rax, [rbp+3Fh+arg_30]
0x14001960a  xor     esi, esi
0x14001960c  movups  xmm0, cs:DEVPKEY_DasParam_PerUserSid
0x140019613  mov     r12, [rbp+3Fh+arg_20]
0x140019617  mov     r15d, r9d
0x14001961a  mov     r13, [rbp+3Fh+arg_28]
0x14001961e  mov     r9, rdx
0x140019621  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140019625  mov     [rbp+3Fh+var_A0], rax
0x140019629  mov     eax, cs:dword_140021538
0x14001962f  mov     r14, rcx
0x140019632  mov     rcx, [rcx+10h]
0x140019636  mov     [rbp+3Fh+var_A8], rsi
0x14001963a  mov     [rbp+3Fh+var_B0], dl
0x14001963d  movaps  [rbp+3Fh+var_90], xmm0
0x140019641  mov     [rbp+3Fh+var_80], eax
0x140019644  mov     [rbp+3Fh+var_7C], 12h
0x14001964b  test    rcx, rcx
0x14001964e  jz      short loc_140019665
0x140019650  inc     rdx
0x140019653  cmp     [rcx+rdx*2], si
0x140019657  jnz     short loc_140019650
0x140019659  lea     eax, ds:2[rdx*2]
0x140019660  mov     [rbp+3Fh+var_78], eax
0x140019663  jmp     short loc_140019668
0x140019665  mov     [rbp+3Fh+var_78], esi
0x140019668  mov     rax, cs:DEVPKEY_DasParam_AepStoreOnly
0x14001966f  lea     r8, [rbp+3Fh+var_A8]
0x140019673  movsd   xmm0, cs:qword_140021650
0x14001967b  mov     rdx, r9; unsigned __int16 *
0x14001967e  mov     [rbp+3Fh+var_68], rax
0x140019682  mov     eax, cs:dword_140021658
0x140019688  mov     [rbp+3Fh+var_58], eax
0x14001968b  lea     rax, [rbp+3Fh+var_B0]
0x14001968f  mov     [rbp+3Fh+var_70], rcx
0x140019693  mov     rcx, [r14+18h]; unsigned __int16 *
0x140019697  mov     [rbp+3Fh+var_48], rax
0x14001969b  movsd   [rbp+3Fh+var_60], xmm0
0x1400196a0  mov     [rbp+3Fh+var_54], 11h
0x1400196a7  mov     [rbp+3Fh+var_50], 1
0x1400196ae  call    DafMakeAepId
0x1400196b3  mov     ebx, eax
0x1400196b5  test    eax, eax
0x1400196b7  js      short loc_140019728
0x1400196b9  lea     rcx, [r14+30h]; lpCriticalSection
0x1400196bd  call    cs:__imp_EnterCriticalSection
0x1400196c3  cmp     [r14+20h], esi
0x1400196c7  jz      short loc_140019719
0x1400196c9  mov     rax, [r14+10h]
0x1400196cd  lea     rcx, [rbp+3Fh+var_90]
0x1400196d1  test    rax, rax
0x1400196d4  lea     rdx, [rbp+3Fh+var_68]
0x1400196d8  mov     r9d, r15d
0x1400196db  cmovnz  rdx, rcx
0x1400196df  neg     rax
0x1400196e2  mov     rax, [rbp+3Fh+var_A0]
0x1400196e6  sbb     ecx, ecx
0x1400196e8  mov     [rsp+100h+var_C0], rax
0x1400196ed  neg     ecx
0x1400196ef  mov     [rsp+100h+var_C8], r13
0x1400196f4  mov     [rsp+100h+var_D0], rdx
0x1400196f9  inc     ecx
0x1400196fb  mov     rdx, [rbp+3Fh+var_A8]
0x1400196ff  xor     r8d, r8d
0x140019702  mov     [rsp+100h+var_D8], ecx
0x140019706  mov     [rsp+100h+var_E0], r12
0x14001970b  lea     ecx, [r8+5]
0x14001970f  call    cs:__imp_DevGetObjectPropertiesEx
0x140019715  mov     ebx, eax
0x140019717  jmp     short loc_14001971E
0x140019719  mov     ebx, 80640013h
0x14001971e  lea     rcx, [r14+30h]; lpCriticalSection
0x140019722  call    cs:__imp_LeaveCriticalSection
0x140019728  cmp     [rbp+3Fh+var_A8], rsi
0x14001972c  jz      short loc_140019737
0x14001972e  mov     rcx, [rbp+3Fh+var_A8]; void *
0x140019732  call    MIDL_user_free
0x140019737  mov     eax, ebx
0x140019739  mov     rcx, [rbp+3Fh+var_40]
0x14001973d  xor     rcx, rsp; StackCookie
0x140019740  call    __security_check_cookie
0x140019745  add     rsp, 0D0h
0x14001974c  pop     r15
0x14001974e  pop     r14
0x140019750  pop     r13
0x140019752  pop     r12
0x140019754  pop     rsi
0x140019755  pop     rbx
0x140019756  pop     rbp
0x140019757  retn
```
