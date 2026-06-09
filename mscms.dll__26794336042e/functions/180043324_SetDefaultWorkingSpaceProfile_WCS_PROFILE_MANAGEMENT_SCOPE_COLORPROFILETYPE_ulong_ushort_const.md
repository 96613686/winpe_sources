# SetDefaultWorkingSpaceProfile(WCS_PROFILE_MANAGEMENT_SCOPE,COLORPROFILETYPE,ulong,ushort const *)

- ea: `0x180043324`
- end: `0x180043443`
- name: `?SetDefaultWorkingSpaceProfile@@YAKW4WCS_PROFILE_MANAGEMENT_SCOPE@@W4COLORPROFILETYPE@@KPEBG@Z`
- size: `287`
- prototype: `unsigned int __fastcall(enum WCS_PROFILE_MANAGEMENT_SCOPE, enum COLORPROFILETYPE, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002435c`

## callees

- `0x18002e5f0`
- `0x180043324`
- `0x18004387c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180043420`
- `ntdll!EtwEventWrite` at `0x180043420`

## pseudocode

```c
__int64 __fastcall SetDefaultWorkingSpaceProfile(
        enum WCS_PROFILE_MANAGEMENT_SCOPE a1,
        enum COLORPROFILETYPE a2,
        unsigned int a3,
        const unsigned __int16 *a4)
{
  char v5; // esi^3
  unsigned int v6; // edi
  unsigned int v7; // r14d
  signed int i; // r8d
  __int64 v9; // rdx
  char *v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 *v14; // rdx
  __int64 v15; // rcx
  int v17; // [rsp+20h] [rbp-60h] BYREF
  enum WCS_PROFILE_MANAGEMENT_SCOPE v18; // [rsp+28h] [rbp-58h] BYREF
  _WORD *v19; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v20[2]; // [rsp+38h] [rbp-48h]
  int v21; // [rsp+48h] [rbp-38h]
  int v22; // [rsp+4Ch] [rbp-34h]
  _WORD v23[8]; // [rsp+60h] [rbp-20h] BYREF

  v18 = a1;
  v5 = HIBYTE(a3);
  v6 = 1;
  v7 = SetProfileForProfileID(a1, a3, a4, 1);
  if ( !v7 )
  {
    HIBYTE(v17) = v5;
    for ( i = 0; (unsigned int)i < 4; ++i )
    {
      v9 = i;
      v10 = (char *)&v17 - i + 3;
      v23[v9] = *v10;
    }
    v11 = -1;
    v23[4] = 0;
    v12 = -1;
    do
      ++v12;
    while ( v23[v12] );
    v20[0] = (unsigned int)(2 * v12 + 2);
    v19 = v23;
    if ( a4 )
    {
      do
        ++v11;
      while ( a4[v11] );
      v20[1] = a4;
      v21 = 2 * v11 + 2;
      v6 = 2;
      v22 = 0;
    }
    v13 = 2LL * v6;
    v14 = SET_DEFAULT_WORKING_SPACE_PROFILE;
    v20[v13 - 1] = &v18;
    v15 = g_etwHandle;
    v20[v13] = 4;
    if ( !a4 )
      v14 = UNSET_DEFAULT_WORKING_SPACE_PROFILE;
    EtwEventWrite(v15, v14, v6 + 1, &v19);
  }
  return v7;
}

```

## disassembly

```asm
0x180043324  push    rbp
0x180043326  push    rbx
0x180043327  push    rsi
0x180043328  push    rdi
0x180043329  push    r14
0x18004332b  mov     rbp, rsp
0x18004332e  sub     rsp, 80h
0x180043335  mov     rax, cs:__security_cookie
0x18004333c  xor     rax, rsp
0x18004333f  mov     [rbp+var_10], rax
0x180043343  mov     rbx, r9
0x180043346  mov     [rbp+var_58], ecx
0x180043349  mov     esi, r8d
0x18004334c  mov     edi, 1
0x180043351  mov     r9d, edi; int
0x180043354  mov     r8, rbx; unsigned __int16 *
0x180043357  mov     edx, esi; unsigned int
0x180043359  call    ?SetProfileForProfileID@@YAKW4WCS_PROFILE_MANAGEMENT_SCOPE@@KPEBGH@Z; SetProfileForProfileID(WCS_PROFILE_MANAGEMENT_SCOPE,ulong,ushort const *,int)
0x18004335e  xor     r9d, r9d
0x180043361  mov     r14d, eax
0x180043364  test    eax, eax
0x180043366  jnz     loc_180043426
0x18004336c  mov     [rbp+var_60], esi
0x18004336f  mov     r8d, r9d
0x180043372  movsxd  rdx, r8d
0x180043375  lea     rcx, [rbp+var_60+3]
0x180043379  sub     rcx, rdx
0x18004337c  add     r8d, edi
0x18004337f  movsx   eax, byte ptr [rcx]
0x180043382  mov     [rbp+rdx*2+var_20], ax
0x180043387  cmp     r8d, 4
0x18004338b  jb      short loc_180043372
0x18004338d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180043391  mov     [rbp+var_18], r9w
0x180043396  mov     rax, rcx
0x180043399  lea     rdx, [rbp+var_20]
0x18004339d  inc     rax
0x1800433a0  cmp     [rdx+rax*2], r9w
0x1800433a5  jnz     short loc_18004339D
0x1800433a7  mov     dword ptr [rbp+var_48+4], r9d
0x1800433ab  lea     rax, ds:2[rax*2]
0x1800433b3  mov     dword ptr [rbp+var_48], eax
0x1800433b6  lea     rdx, [rbp+var_20]
0x1800433ba  mov     [rbp+var_50], rdx
0x1800433be  test    rbx, rbx
0x1800433c1  jz      short loc_1800433E5
0x1800433c3  inc     rcx
0x1800433c6  cmp     [rbx+rcx*2], r9w
0x1800433cb  jnz     short loc_1800433C3
0x1800433cd  lea     rax, ds:2[rcx*2]
0x1800433d5  mov     [rbp+var_40], rbx
0x1800433d9  mov     [rbp+var_38], eax
0x1800433dc  mov     edi, 2
0x1800433e1  mov     [rbp+var_34], r9d
0x1800433e5  lea     rcx, [rbp+var_58]
0x1800433e9  mov     eax, edi
0x1800433eb  add     rax, rax
0x1800433ee  lea     rdx, SET_DEFAULT_WORKING_SPACE_PROFILE
0x1800433f5  test    rbx, rbx
0x1800433f8  lea     r8d, [rdi+1]
0x1800433fc  lea     r9, [rbp+var_50]
0x180043400  mov     [rbp+rax*8+var_50], rcx
0x180043405  mov     rcx, cs:g_etwHandle
0x18004340c  mov     [rbp+rax*8+var_48], 4
0x180043415  lea     rax, UNSET_DEFAULT_WORKING_SPACE_PROFILE
0x18004341c  cmovz   rdx, rax
0x180043420  call    cs:__imp_EtwEventWrite
0x180043426  mov     eax, r14d
0x180043429  mov     rcx, [rbp+var_10]
0x18004342d  xor     rcx, rsp; StackCookie
0x180043430  call    __security_check_cookie
0x180043435  add     rsp, 80h
0x18004343c  pop     r14
0x18004343e  pop     rdi
0x18004343f  pop     rsi
0x180043440  pop     rbx
0x180043441  pop     rbp
0x180043442  retn
```
