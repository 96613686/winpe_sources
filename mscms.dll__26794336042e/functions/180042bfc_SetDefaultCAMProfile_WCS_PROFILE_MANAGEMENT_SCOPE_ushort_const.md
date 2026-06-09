# SetDefaultCAMProfile(WCS_PROFILE_MANAGEMENT_SCOPE,ushort const *)

- ea: `0x180042bfc`
- end: `0x180042cc4`
- name: `?SetDefaultCAMProfile@@YAKW4WCS_PROFILE_MANAGEMENT_SCOPE@@PEBG@Z`
- size: `200`
- prototype: `unsigned int __fastcall(enum WCS_PROFILE_MANAGEMENT_SCOPE, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002435c`

## callees

- `0x18002e5f0`
- `0x180042bfc`
- `0x18004387c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180042ca4`
- `ntdll!EtwEventWrite` at `0x180042ca4`

## pseudocode

```c
__int64 __fastcall SetDefaultCAMProfile(enum WCS_PROFILE_MANAGEMENT_SCOPE a1, const unsigned __int16 *a2)
{
  unsigned int v3; // edi
  unsigned int v4; // r8d
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 *v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rcx
  enum WCS_PROFILE_MANAGEMENT_SCOPE v11; // [rsp+20h] [rbp-38h] BYREF
  const unsigned __int16 *v12; // [rsp+28h] [rbp-30h] BYREF
  _QWORD v13[3]; // [rsp+30h] [rbp-28h]

  v11 = a1;
  v3 = SetProfileForProfileID(a1, 0x63616D70u, a2, 0);
  if ( !v3 )
  {
    v4 = 0;
    if ( a2 )
    {
      v5 = -1;
      do
        ++v5;
      while ( a2[v5] );
      v12 = a2;
      v13[0] = (unsigned int)(2 * v5 + 2);
      v4 = 1;
    }
    v6 = 2LL * v4;
    v7 = SET_DEFAULT_CAMP_PROFILE;
    v8 = v4 + 1;
    v13[v6 - 1] = &v11;
    v9 = g_etwHandle;
    v13[v6] = 4;
    if ( !a2 )
      v7 = UNSET_DEFAULT_CAMP_PROFILE;
    EtwEventWrite(v9, v7, v8, &v12);
  }
  return v3;
}

```

## disassembly

```asm
0x180042bfc  mov     [rsp+arg_10], rbx
0x180042c01  push    rdi
0x180042c02  sub     rsp, 50h
0x180042c06  mov     rax, cs:__security_cookie
0x180042c0d  xor     rax, rsp
0x180042c10  mov     [rsp+58h+var_10], rax
0x180042c15  mov     rbx, rdx
0x180042c18  mov     [rsp+58h+var_38], ecx
0x180042c1c  mov     r8, rdx; unsigned __int16 *
0x180042c1f  xor     r9d, r9d; int
0x180042c22  mov     edx, 63616D70h; unsigned int
0x180042c27  call    ?SetProfileForProfileID@@YAKW4WCS_PROFILE_MANAGEMENT_SCOPE@@KPEBGH@Z; SetProfileForProfileID(WCS_PROFILE_MANAGEMENT_SCOPE,ulong,ushort const *,int)
0x180042c2c  xor     r9d, r9d
0x180042c2f  mov     edi, eax
0x180042c31  test    eax, eax
0x180042c33  jnz     short loc_180042CAA
0x180042c35  mov     r8d, r9d
0x180042c38  test    rbx, rbx
0x180042c3b  jz      short loc_180042C67
0x180042c3d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180042c41  inc     rax
0x180042c44  cmp     [rbx+rax*2], r9w
0x180042c49  jnz     short loc_180042C41
0x180042c4b  lea     rax, ds:2[rax*2]
0x180042c53  mov     [rsp+58h+var_30], rbx
0x180042c58  mov     dword ptr [rsp+58h+var_28], eax
0x180042c5c  mov     r8d, 1
0x180042c62  mov     dword ptr [rsp+58h+var_28+4], r9d
0x180042c67  mov     eax, r8d
0x180042c6a  lea     rcx, [rsp+58h+var_38]
0x180042c6f  add     rax, rax
0x180042c72  lea     rdx, SET_DEFAULT_CAMP_PROFILE
0x180042c79  inc     r8d
0x180042c7c  lea     r9, [rsp+58h+var_30]
0x180042c81  test    rbx, rbx
0x180042c84  mov     [rsp+rax*8+58h+var_30], rcx
0x180042c89  mov     rcx, cs:g_etwHandle
0x180042c90  mov     [rsp+rax*8+58h+var_28], 4
0x180042c99  lea     rax, UNSET_DEFAULT_CAMP_PROFILE
0x180042ca0  cmovz   rdx, rax
0x180042ca4  call    cs:__imp_EtwEventWrite
0x180042caa  mov     eax, edi
0x180042cac  mov     rcx, [rsp+58h+var_10]
0x180042cb1  xor     rcx, rsp; StackCookie
0x180042cb4  call    __security_check_cookie
0x180042cb9  mov     rbx, [rsp+58h+arg_10]
0x180042cbe  add     rsp, 50h
0x180042cc2  pop     rdi
0x180042cc3  retn
```
