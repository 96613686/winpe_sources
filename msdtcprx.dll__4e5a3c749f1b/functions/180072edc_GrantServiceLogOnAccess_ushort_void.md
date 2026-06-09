# GrantServiceLogOnAccess(ushort *,void *)

- ea: `0x180072edc`
- end: `0x1800730c0`
- name: `?GrantServiceLogOnAccess@@YAJPEAGPEAX@Z`
- size: `484`
- prototype: `__int64 __fastcall(unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180073a3c`

## callees

- `0x180011ac0`
- `0x180072b4c`
- `0x180072edc`
- `0x1800730c8`
- `0x180085010`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180073087`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180073096`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180073087`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180073096`

## string_xrefs

- `0x180072f34`: `com\complus\dtc\shared\util\security.cpp`
- `0x180073070`: `com\complus\dtc\shared\util\security.cpp`
- `0x180072f3b`: `InstallDTC: LSAPrivate.Init() failed`
- `0x180072fc0`: `InstallDTC: LSAPrivate.LsaOpenPolicy failed`
- `0x180073010`: `InstallDTC: LsaCreateAccount || LsaOpenAccount failed`
- `0x180073038`: `InstallDTC: LsaGetSystemAccessAccount failed`
- `0x180073063`: `InstallDTC: LsaSetSystemAccessAccount failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GrantServiceLogOnAccess(unsigned __int16 *a1, void *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // r9d
  char *v9; // rdx
  LSA_HANDLE v11; // [rsp+30h] [rbp-39h] BYREF
  _DWORD v12[2]; // [rsp+38h] [rbp-31h] BYREF
  unsigned __int16 *v13; // [rsp+40h] [rbp-29h]
  __int64 v14; // [rsp+48h] [rbp-21h] BYREF
  __int64 (__fastcall *v15)(_DWORD *, __int64 *, __int64, LSA_HANDLE *); // [rsp+50h] [rbp-19h]
  __int64 (__fastcall *v16)(LSA_HANDLE, void *, __int64, LSA_HANDLE *); // [rsp+58h] [rbp-11h]
  __int64 (__fastcall *v17)(LSA_HANDLE, void *, __int64, LSA_HANDLE *); // [rsp+60h] [rbp-9h]
  __int64 (__fastcall *v18)(LSA_HANDLE, int *); // [rsp+68h] [rbp-1h]
  __int64 (__fastcall *v19)(LSA_HANDLE, _QWORD); // [rsp+70h] [rbp+7h]
  __int64 v20; // [rsp+78h] [rbp+Fh] BYREF
  __int128 v21; // [rsp+80h] [rbp+17h]
  __int128 v22; // [rsp+90h] [rbp+27h]
  __int64 v23; // [rsp+A0h] [rbp+37h]
  int v24; // [rsp+E0h] [rbp+77h] BYREF
  LSA_HANDLE ObjectHandle; // [rsp+E8h] [rbp+7Fh] BYREF

  v11 = 0;
  ObjectHandle = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v14 = 0;
  v4 = CLSAPrivate::Init((CLSAPrivate *)&v14);
  v5 = v4;
  if ( v4 < 0 )
  {
    TraceFile(v4, "InstallDTC: LSAPrivate.Init() failed", "com\\complus\\dtc\\shared\\util\\security.cpp", 0x3C5u);
    goto LABEL_24;
  }
  v20 = 48;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v12[1] = 0;
  if ( a1 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a1[v6] );
    LOWORD(v12[0]) = 2 * v6;
    HIWORD(v12[0]) = 2 * v6 + 2;
    v13 = a1;
  }
  else
  {
    v12[0] = 0;
    v13 = 0;
  }
  v7 = v15(v12, &v20, 987135, &v11);
  if ( v7 >= 0 )
  {
    v7 = v16(v11, a2, 983055, &ObjectHandle);
    if ( v7 == -1073741772 )
      v7 = v17(v11, a2, 983055, &ObjectHandle);
    if ( v7 >= 0 )
    {
      v24 = 0;
      v7 = v18(ObjectHandle, &v24);
      if ( v7 >= 0 )
      {
        if ( (v24 & 0x10) != 0 )
          goto LABEL_20;
        v7 = v19(ObjectHandle, v24 | 0x10u);
        if ( v7 >= 0 )
          goto LABEL_20;
        v8 = 1072;
        v9 = "InstallDTC: LsaSetSystemAccessAccount failed";
      }
      else
      {
        v8 = 1054;
        v9 = "InstallDTC: LsaGetSystemAccessAccount failed";
      }
    }
    else
    {
      v8 = 1037;
      v9 = "InstallDTC: LsaCreateAccount || LsaOpenAccount failed";
    }
  }
  else
  {
    v8 = 1007;
    v9 = "InstallDTC: LSAPrivate.LsaOpenPolicy failed";
  }
  v5 = v7 | 0x10000000;
  TraceFile(v7 | 0x10000000, v9, "com\\complus\\dtc\\shared\\util\\security.cpp", v8);
LABEL_20:
  if ( ObjectHandle )
    LsaClose(ObjectHandle);
  if ( v11 )
    LsaClose(v11);
LABEL_24:
  CLSAPrivate::~CLSAPrivate((CLSAPrivate *)&v14);
  return v5;
}

```

## disassembly

```asm
0x180072edc  mov     [rsp-8+arg_0], rbx
0x180072ee1  mov     [rsp-8+arg_8], rsi
0x180072ee6  push    rbp
0x180072ee7  push    rdi
0x180072ee8  push    r14
0x180072eea  lea     rbp, [rsp-47h]
0x180072eef  sub     rsp, 0B0h
0x180072ef6  mov     rsi, rdx
0x180072ef9  mov     rdi, rcx
0x180072efc  xor     r14d, r14d
0x180072eff  mov     [rbp+57h+var_90], r14
0x180072f03  mov     [rbp+57h+ObjectHandle], r14
0x180072f07  mov     [rbp+57h+var_70], r14
0x180072f0b  mov     [rbp+57h+var_68], r14
0x180072f0f  mov     [rbp+57h+var_60], r14
0x180072f13  mov     [rbp+57h+var_58], r14
0x180072f17  mov     [rbp+57h+var_50], r14
0x180072f1b  mov     [rbp+57h+var_78], r14
0x180072f1f  lea     rcx, [rbp+57h+var_78]; this
0x180072f23  call    ?Init@CLSAPrivate@@QEAAJXZ; CLSAPrivate::Init(void)
0x180072f28  mov     ebx, eax
0x180072f2a  test    eax, eax
0x180072f2c  jns     short loc_180072F4E
0x180072f2e  mov     r9d, 3C5h; unsigned int
0x180072f34  lea     r8, aComComplusDtcS_9; "com\\complus\\dtc\\shared\\util\\securi"...
0x180072f3b  lea     rdx, aInstalldtcLsap_0; "InstallDTC: LSAPrivate.Init() failed"
0x180072f42  mov     ecx, eax; int
0x180072f44  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180072f49  jmp     loc_18007309D
0x180072f4e  mov     [rbp+57h+var_48], 30h ; '0'
0x180072f56  xorps   xmm0, xmm0
0x180072f59  xor     eax, eax
0x180072f5b  movups  [rbp+57h+var_40], xmm0
0x180072f5f  movups  [rbp+57h+var_30], xmm0
0x180072f63  mov     [rbp+57h+var_20], rax
0x180072f67  mov     [rbp+57h+var_84], r14d
0x180072f6b  test    rdi, rdi
0x180072f6e  jz      short loc_180072F93
0x180072f70  or      rax, 0FFFFFFFFFFFFFFFFh
0x180072f74  inc     rax
0x180072f77  cmp     [rdi+rax*2], r14w
0x180072f7c  jnz     short loc_180072F74
0x180072f7e  add     ax, ax
0x180072f81  mov     word ptr [rbp+57h+var_88], ax
0x180072f85  add     ax, 2
0x180072f89  mov     word ptr [rbp+57h+var_88+2], ax
0x180072f8d  mov     [rbp+57h+var_80], rdi
0x180072f91  jmp     short loc_180072F9B
0x180072f93  mov     [rbp+57h+var_88], r14d
0x180072f97  mov     [rbp+57h+var_80], r14
0x180072f9b  lea     r9, [rbp+57h+var_90]
0x180072f9f  mov     r8d, 0F0FFFh
0x180072fa5  lea     rdx, [rbp+57h+var_48]
0x180072fa9  lea     rcx, [rbp+57h+var_88]
0x180072fad  mov     rax, [rbp+57h+var_70]
0x180072fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072fb6  test    eax, eax
0x180072fb8  jns     short loc_180072FCC
0x180072fba  mov     r9d, 3EFh
0x180072fc0  lea     rdx, aInstalldtcLsap; "InstallDTC: LSAPrivate.LsaOpenPolicy fa"...
0x180072fc7  jmp     loc_18007306A
0x180072fcc  lea     r9, [rbp+57h+ObjectHandle]
0x180072fd0  mov     edi, 0F000Fh
0x180072fd5  mov     r8d, edi
0x180072fd8  mov     rdx, rsi
0x180072fdb  mov     rcx, [rbp+57h+var_90]
0x180072fdf  mov     rax, [rbp+57h+var_68]
0x180072fe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072fe8  cmp     eax, 0C0000034h
0x180072fed  jnz     short loc_180073006
0x180072fef  lea     r9, [rbp+57h+ObjectHandle]
0x180072ff3  mov     r8d, edi
0x180072ff6  mov     rdx, rsi
0x180072ff9  mov     rcx, [rbp+57h+var_90]
0x180072ffd  mov     rax, [rbp+57h+var_60]
0x180073001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073006  test    eax, eax
0x180073008  jns     short loc_180073019
0x18007300a  mov     r9d, 40Dh
0x180073010  lea     rdx, aInstalldtcLsac; "InstallDTC: LsaCreateAccount || LsaOpen"...
0x180073017  jmp     short loc_18007306A
0x180073019  mov     [rbp+57h+arg_10], r14d
0x18007301d  lea     rdx, [rbp+57h+arg_10]
0x180073021  mov     rcx, [rbp+57h+ObjectHandle]
0x180073025  mov     rax, [rbp+57h+var_58]
0x180073029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007302e  test    eax, eax
0x180073030  jns     short loc_180073041
0x180073032  mov     r9d, 41Eh
0x180073038  lea     rdx, aInstalldtcLsag; "InstallDTC: LsaGetSystemAccessAccount f"...
0x18007303f  jmp     short loc_18007306A
0x180073041  mov     edx, [rbp+57h+arg_10]
0x180073044  test    dl, 10h
0x180073047  jnz     short loc_18007307E
0x180073049  or      edx, 10h
0x18007304c  mov     rcx, [rbp+57h+ObjectHandle]
0x180073050  mov     rax, [rbp+57h+var_50]
0x180073054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073059  test    eax, eax
0x18007305b  jns     short loc_18007307E
0x18007305d  mov     r9d, 430h; unsigned int
0x180073063  lea     rdx, aInstalldtcLsas; "InstallDTC: LsaSetSystemAccessAccount f"...
0x18007306a  mov     ebx, eax
0x18007306c  bts     ebx, 1Ch
0x180073070  lea     r8, aComComplusDtcS_9; "com\\complus\\dtc\\shared\\util\\securi"...
0x180073077  mov     ecx, ebx; int
0x180073079  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18007307e  mov     rcx, [rbp+57h+ObjectHandle]; ObjectHandle
0x180073082  test    rcx, rcx
0x180073085  jz      short loc_18007308D
0x180073087  call    cs:__imp_LsaClose
0x18007308d  mov     rcx, [rbp+57h+var_90]; ObjectHandle
0x180073091  test    rcx, rcx
0x180073094  jz      short loc_18007309D
0x180073096  call    cs:__imp_LsaClose
0x18007309c  nop
0x18007309d  lea     rcx, [rbp+57h+var_78]; this
0x1800730a1  call    ??1CLSAPrivate@@QEAA@XZ; CLSAPrivate::~CLSAPrivate(void)
0x1800730a6  mov     eax, ebx
0x1800730a8  lea     r11, [rsp+0C0h+var_10]
0x1800730b0  mov     rbx, [r11+20h]
0x1800730b4  mov     rsi, [r11+28h]
0x1800730b8  mov     rsp, r11
0x1800730bb  pop     r14
0x1800730bd  pop     rdi
0x1800730be  pop     rbp
0x1800730bf  retn
```
