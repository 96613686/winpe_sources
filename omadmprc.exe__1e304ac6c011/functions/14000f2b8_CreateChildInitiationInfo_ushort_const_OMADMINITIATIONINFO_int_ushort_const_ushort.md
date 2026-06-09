# CreateChildInitiationInfo(ushort const *,OMADMINITIATIONINFO *,int,ushort const *,ushort * *)

- ea: `0x14000f2b8`
- end: `0x14000f57a`
- name: `?CreateChildInitiationInfo@@YAJPEBGPEAUOMADMINITIATIONINFO@@H0PEAPEAG@Z`
- size: `706`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct OMADMINITIATIONINFO *, int, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140011468`
- `0x140013350`

## callees

- `0x14000271f`
- `0x140008504`
- `0x140008ea0`
- `0x14000f2b8`
- `0x140015690`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000f475`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000f475`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000f50d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000f521`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000f50d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000f521`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14000f391`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14000f391`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x14000f3ba`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x14000f3ba`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x14000f49d`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x14000f49d`
- `DMCmnUtils!CopyString` at `0x14000f53a`
- `DMCmnUtils!CopyString` at `0x14000f53a`
- `DMCmnUtils!OmaDmRegistrySetString` at `0x14000f44f`
- `DMCmnUtils!OmaDmRegistrySetString` at `0x14000f44f`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x14000f4dc`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x14000f4dc`
- `omadmapi!__imp_OmaDmSetInitiationInfo` at `0x14000f418`
- `omadmapi!__imp_OmaDmSetInitiationInfo` at `0x14000f418`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateChildInitiationInfo(
        const unsigned __int16 *a1,
        struct OMADMINITIATIONINFO *a2,
        unsigned int a3,
        OLECHAR *a4,
        unsigned __int16 **a5)
{
  __int64 v9; // rax
  __int64 v10; // r8
  OLECHAR *v11; // rcx
  OLECHAR v12; // dx
  HRESULT v13; // ebx
  OLECHAR *v14; // rdx
  __int64 v15; // rdx
  HRESULT DWORD; // eax
  unsigned __int64 v18; // r9
  __int64 v19; // rdx
  int v20; // eax
  int v21; // [rsp+20h] [rbp-E0h]
  unsigned int v22; // [rsp+30h] [rbp-D0h] BYREF
  GUID pguid; // [rsp+38h] [rbp-C8h] BYREF
  OLECHAR sz[256]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v25[264]; // [rsp+250h] [rbp+150h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4A8h] [rbp+3A8h]

  memset_0(sz, 0, sizeof(sz));
  if ( a4 )
  {
    v9 = 2147483646;
    v10 = 256;
    v11 = sz;
    do
    {
      if ( !v9 )
        break;
      v12 = *a4;
      if ( !*a4 )
        break;
      ++a4;
      *v11++ = v12;
      --v9;
      --v10;
    }
    while ( v10 );
    v13 = v10 == 0 ? 0x8007007A : 0;
    v14 = v11 - 1;
    if ( v10 )
      v14 = v11;
    *v14 = 0;
    if ( !v10 )
    {
      v15 = 1203;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmprc\\omadmprc.cpp",
        (const char *)(unsigned int)v13,
        v21);
      return (unsigned int)v13;
    }
  }
  else
  {
    pguid = 0;
    v13 = CoCreateGuid(&pguid);
    if ( v13 < 0 )
    {
      v15 = 1208;
      goto LABEL_10;
    }
    if ( !StringFromGUID2(&pguid, sz, 256) )
    {
      v13 = -2147418113;
      v15 = 1209;
      goto LABEL_10;
    }
  }
  v13 = StringCchPrintfW(v25, 0x104u, L"%s\\%s", a1, sz);
  if ( v13 < 0 )
  {
    v15 = 1218;
    goto LABEL_10;
  }
  v13 = OmaDmSetInitiationInfo(v25, a2, a3);
  if ( v13 < 0 )
  {
    v15 = 1220;
    goto LABEL_10;
  }
  v13 = OmaDmRegistrySetString(HKEY_LOCAL_MACHINE, v25, L"ParentInitiationId", a1);
  if ( v13 < 0 )
  {
    v15 = 1221;
    goto LABEL_10;
  }
  EnterCriticalSection(&stru_140024310);
  *(_QWORD *)&pguid.Data1 = &stru_140024310;
  v22 = 0;
  DWORD = OmaDmRegistryGetDWORD(HKEY_LOCAL_MACHINE, a1, L"ChildCount", &v22);
  v13 = 0;
  if ( DWORD != -2147024894 )
    v13 = DWORD;
  if ( v13 < 0 )
  {
    v18 = (unsigned int)v13;
    v19 = 1231;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmprc\\omadmprc.cpp",
      (const char *)v18,
      v21);
    LeaveCriticalSection(&stru_140024310);
    return (unsigned int)v13;
  }
  v20 = OmaDmRegistrySetDWORD(HKEY_LOCAL_MACHINE, a1, L"ChildCount", ++v22);
  v13 = v20;
  if ( v20 < 0 )
  {
    v18 = (unsigned int)v20;
    v19 = 1233;
    goto LABEL_28;
  }
  LeaveCriticalSection(&stru_140024310);
  v13 = CopyString(v25, 0xFFFFFFFF, a5);
  if ( v13 < 0 )
  {
    v15 = 1236;
    goto LABEL_10;
  }
  return 0;
}

```

## disassembly

```asm
0x14000f2b8  push    rbp
0x14000f2ba  push    rbx
0x14000f2bb  push    rsi
0x14000f2bc  push    rdi
0x14000f2bd  push    r12
0x14000f2bf  push    r14
0x14000f2c1  push    r15
0x14000f2c3  lea     rbp, [rsp-370h]
0x14000f2cb  sub     rsp, 470h
0x14000f2d2  mov     rax, cs:__security_cookie
0x14000f2d9  xor     rax, rsp
0x14000f2dc  mov     [rbp+3A0h+var_40], rax
0x14000f2e3  mov     rbx, r9
0x14000f2e6  mov     r14d, r8d
0x14000f2e9  mov     rsi, rdx
0x14000f2ec  mov     rdi, rcx
0x14000f2ef  mov     r15, [rbp+3A0h+arg_20]
0x14000f2f6  xor     edx, edx; Val
0x14000f2f8  mov     r8d, 200h; Size
0x14000f2fe  lea     rcx, [rsp+4A0h+sz]; void *
0x14000f303  call    memset_0
0x14000f308  xor     r12d, r12d
0x14000f30b  test    rbx, rbx
0x14000f30e  jz      short loc_14000F384
0x14000f310  mov     eax, 7FFFFFFEh
0x14000f315  mov     r8d, 100h
0x14000f31b  lea     rcx, [rsp+4A0h+sz]
0x14000f320  test    rax, rax
0x14000f323  jz      short loc_14000F341
0x14000f325  movzx   edx, word ptr [rbx]
0x14000f328  test    dx, dx
0x14000f32b  jz      short loc_14000F341
0x14000f32d  add     rbx, 2
0x14000f331  mov     [rcx], dx
0x14000f334  add     rcx, 2
0x14000f338  dec     rax
0x14000f33b  sub     r8, 1
0x14000f33f  jnz     short loc_14000F320
0x14000f341  mov     rax, r8
0x14000f344  neg     rax
0x14000f347  sbb     ebx, ebx
0x14000f349  not     ebx
0x14000f34b  and     ebx, 8007007Ah
0x14000f351  lea     rdx, [rcx-2]
0x14000f355  test    r8, r8
0x14000f358  cmovnz  rdx, rcx
0x14000f35c  mov     [rdx], r12w
0x14000f360  jnz     short loc_14000F3D6
0x14000f362  mov     edx, 4B3h; void *
0x14000f367  mov     rcx, [rbp+3A8h]; this
0x14000f36e  mov     r9d, ebx; char *
0x14000f371  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\omadm\\omadmprc"...
0x14000f378  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000f37d  mov     eax, ebx
0x14000f37f  jmp     loc_14000F558
0x14000f384  xorps   xmm0, xmm0
0x14000f387  movups  xmmword ptr [rsp+4A0h+pguid.Data1], xmm0
0x14000f38c  lea     rcx, [rsp+4A0h+pguid]; pguid
0x14000f391  call    cs:__imp_CoCreateGuid
0x14000f398  nop     dword ptr [rax+rax+00h]
0x14000f39d  mov     ebx, eax
0x14000f39f  test    eax, eax
0x14000f3a1  jns     short loc_14000F3AA
0x14000f3a3  mov     edx, 4B8h
0x14000f3a8  jmp     short loc_14000F367
0x14000f3aa  mov     r8d, 100h; cchMax
0x14000f3b0  lea     rdx, [rsp+4A0h+sz]; lpsz
0x14000f3b5  lea     rcx, [rsp+4A0h+pguid]; rguid
0x14000f3ba  call    cs:__imp_StringFromGUID2
0x14000f3c1  nop     dword ptr [rax+rax+00h]
0x14000f3c6  test    eax, eax
0x14000f3c8  jnz     short loc_14000F3D6
0x14000f3ca  mov     ebx, 8000FFFFh
0x14000f3cf  mov     edx, 4B9h
0x14000f3d4  jmp     short loc_14000F367
0x14000f3d6  lea     rax, [rsp+4A0h+sz]
0x14000f3db  mov     qword ptr [rsp+4A0h+var_480], rax; int
0x14000f3e0  mov     r9, rdi
0x14000f3e3  lea     r8, aSS; "%s\\%s"
0x14000f3ea  mov     edx, 104h; unsigned __int64
0x14000f3ef  lea     rcx, [rbp+3A0h+var_250]; unsigned __int16 *
0x14000f3f6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000f3fb  mov     ebx, eax
0x14000f3fd  test    eax, eax
0x14000f3ff  jns     short loc_14000F40B
0x14000f401  mov     edx, 4C2h
0x14000f406  jmp     loc_14000F367
0x14000f40b  mov     r8d, r14d
0x14000f40e  mov     rdx, rsi
0x14000f411  lea     rcx, [rbp+3A0h+var_250]
0x14000f418  call    cs:__imp_OmaDmSetInitiationInfo
0x14000f41f  nop     dword ptr [rax+rax+00h]
0x14000f424  mov     ebx, eax
0x14000f426  test    eax, eax
0x14000f428  jns     short loc_14000F434
0x14000f42a  mov     edx, 4C4h
0x14000f42f  jmp     loc_14000F367
0x14000f434  mov     r9, rdi
0x14000f437  lea     r8, aParentinitiati; "ParentInitiationId"
0x14000f43e  lea     rdx, [rbp+3A0h+var_250]
0x14000f445  mov     r14, 0FFFFFFFF80000002h
0x14000f44c  mov     rcx, r14
0x14000f44f  call    cs:__imp_?OmaDmRegistrySetString@@YAJPEAUHKEY__@@PEBG11@Z; OmaDmRegistrySetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x14000f456  nop     dword ptr [rax+rax+00h]
0x14000f45b  mov     ebx, eax
0x14000f45d  test    eax, eax
0x14000f45f  jns     short loc_14000F46B
0x14000f461  mov     edx, 4C5h
0x14000f466  jmp     loc_14000F367
0x14000f46b  lea     rsi, stru_140024310
0x14000f472  mov     rcx, rsi; lpCriticalSection
0x14000f475  call    cs:__imp_EnterCriticalSection
0x14000f47c  nop     dword ptr [rax+rax+00h]
0x14000f481  mov     qword ptr [rsp+4A0h+pguid.Data1], rsi
0x14000f486  mov     [rsp+4A0h+var_470], r12d
0x14000f48b  lea     r9, [rsp+4A0h+var_470]
0x14000f490  lea     r8, aChildcount; "ChildCount"
0x14000f497  mov     rdx, rdi
0x14000f49a  mov     rcx, r14
0x14000f49d  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x14000f4a4  nop     dword ptr [rax+rax+00h]
0x14000f4a9  mov     ebx, r12d
0x14000f4ac  cmp     eax, 80070002h
0x14000f4b1  cmovnz  ebx, eax
0x14000f4b4  test    ebx, ebx
0x14000f4b6  jns     short loc_14000F4C2
0x14000f4b8  mov     r9d, ebx
0x14000f4bb  mov     edx, 4CFh
0x14000f4c0  jmp     short loc_14000F4F6
0x14000f4c2  mov     r9d, [rsp+4A0h+var_470]
0x14000f4c7  inc     r9d
0x14000f4ca  mov     [rsp+4A0h+var_470], r9d
0x14000f4cf  lea     r8, aChildcount; "ChildCount"
0x14000f4d6  mov     rdx, rdi
0x14000f4d9  mov     rcx, r14
0x14000f4dc  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x14000f4e3  nop     dword ptr [rax+rax+00h]
0x14000f4e8  mov     ebx, eax
0x14000f4ea  test    eax, eax
0x14000f4ec  jns     short loc_14000F51E
0x14000f4ee  mov     r9d, eax; char *
0x14000f4f1  mov     edx, 4D1h; void *
0x14000f4f6  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\omadm\\omadmprc"...
0x14000f4fd  mov     rcx, [rbp+3A8h]; this
0x14000f504  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000f509  nop
0x14000f50a  mov     rcx, rsi; lpCriticalSection
0x14000f50d  call    cs:__imp_LeaveCriticalSection
0x14000f514  nop     dword ptr [rax+rax+00h]
0x14000f519  jmp     loc_14000F37D
0x14000f51e  mov     rcx, rsi; lpCriticalSection
0x14000f521  call    cs:__imp_LeaveCriticalSection
0x14000f528  nop     dword ptr [rax+rax+00h]
0x14000f52d  mov     r8, r15
0x14000f530  or      edx, 0FFFFFFFFh
0x14000f533  lea     rcx, [rbp+3A0h+var_250]
0x14000f53a  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x14000f541  nop     dword ptr [rax+rax+00h]
0x14000f546  mov     ebx, eax
0x14000f548  test    eax, eax
0x14000f54a  jns     short loc_14000F556
0x14000f54c  mov     edx, 4D4h
0x14000f551  jmp     loc_14000F367
0x14000f556  xor     eax, eax
0x14000f558  mov     rcx, [rbp+3A0h+var_40]
0x14000f55f  xor     rcx, rsp; StackCookie
0x14000f562  call    __security_check_cookie
0x14000f567  add     rsp, 470h
0x14000f56e  pop     r15
0x14000f570  pop     r14
0x14000f572  pop     r12
0x14000f574  pop     rdi
0x14000f575  pop     rsi
0x14000f576  pop     rbx
0x14000f577  pop     rbp
0x14000f578  retn
```
