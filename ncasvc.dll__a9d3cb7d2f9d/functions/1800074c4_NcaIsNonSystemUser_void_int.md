# NcaIsNonSystemUser(void *,int *)

- ea: `0x1800074c4`
- end: `0x180007557`
- name: `?NcaIsNonSystemUser@@YAKPEAXPEAH@Z`
- size: `147`
- prototype: `__int64 __fastcall(void *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017708`

## callees

- `0x180004f34`
- `0x1800074c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074fb`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800074eb`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800074eb`

## pseudocode

```c
__int64 __fastcall NcaIsNonSystemUser(void *a1, int *a2)
{
  DWORD LastError; // ebx
  WINBOOL IsMember; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  IsMember = 0;
  if ( CheckTokenMembership(a1, SidToCheck, &IsMember) )
  {
    LastError = 0;
    *a2 = IsMember == 0;
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800074c4  mov     [rsp+arg_0], rbx
0x1800074c9  push    rdi
0x1800074ca  sub     rsp, 20h
0x1800074ce  mov     rdi, rdx
0x1800074d1  mov     dword ptr [rdx], 0
0x1800074d7  mov     rdx, cs:SidToCheck; SidToCheck
0x1800074de  lea     r8, [rsp+28h+IsMember]; IsMember
0x1800074e3  mov     [rsp+28h+IsMember], 0
0x1800074eb  call    cs:__imp_CheckTokenMembership
0x1800074f2  nop     dword ptr [rax+rax+00h]
0x1800074f7  test    eax, eax
0x1800074f9  jnz     short loc_18000753C
0x1800074fb  call    cs:__imp_GetLastError
0x180007502  nop     dword ptr [rax+rax+00h]
0x180007507  mov     ebx, eax
0x180007509  mov     rcx, cs:WPP_GLOBAL_Control
0x180007510  lea     rax, WPP_GLOBAL_Control
0x180007517  cmp     rcx, rax
0x18000751a  jz      short loc_180007549
0x18000751c  test    byte ptr [rcx+1Ch], 1
0x180007520  jz      short loc_180007549
0x180007522  mov     rcx, [rcx+10h]
0x180007526  lea     r8, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids
0x18000752d  mov     edx, 10h
0x180007532  mov     r9d, ebx
0x180007535  call    WPP_SF_d
0x18000753a  jmp     short loc_180007549
0x18000753c  xor     eax, eax
0x18000753e  xor     ebx, ebx
0x180007540  cmp     [rsp+28h+IsMember], eax
0x180007544  setz    al
0x180007547  mov     [rdi], eax
0x180007549  mov     eax, ebx
0x18000754b  mov     rbx, [rsp+28h+arg_0]
0x180007550  add     rsp, 20h
0x180007554  pop     rdi
0x180007555  retn
```
