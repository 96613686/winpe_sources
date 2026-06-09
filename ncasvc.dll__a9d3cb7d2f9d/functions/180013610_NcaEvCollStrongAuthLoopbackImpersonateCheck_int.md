# NcaEvCollStrongAuthLoopbackImpersonateCheck(int *)

- ea: `0x180013610`
- end: `0x1800136d9`
- name: `?NcaEvCollStrongAuthLoopbackImpersonateCheck@@YAXPEAH@Z`
- size: `201`
- prototype: `void __fastcall(int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016ee4`

## callees

- `0x180004f34`
- `0x180013610`
- `0x180013aa8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001364e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001364e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180013637`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180013637`

## pseudocode

```c
void __fastcall NcaEvCollStrongAuthLoopbackImpersonateCheck(int *a1)
{
  DWORD v1; // ebx
  int v3; // r8d
  DWORD LastError; // eax
  PVOID *v5; // rcx
  PVOID v6; // rcx
  const char *v7; // rax
  WINBOOL v8; // [rsp+40h] [rbp+8h] BYREF

  v1 = 0;
  *a1 = 0;
  v8 = 0;
  if ( CheckTokenMembership(0, hMem, &v8) )
  {
    *a1 = v8;
    goto LABEL_6;
  }
  LastError = GetLastError();
  v1 = LastError;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_b3aa15e3641333918320d88489d2b829_Traceguids, LastError);
LABEL_6:
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
  {
    v6 = v5[2];
    v7 = "TRUE";
    if ( v8 != 1 )
      v7 = "FALSE";
    WPP_SF_ds((_DWORD)v6, (unsigned int)"FALSE", v3, v1, (__int64)v7);
  }
}

```

## disassembly

```asm
0x180013610  mov     rax, rsp
0x180013613  mov     [rax+10h], rbx
0x180013617  mov     [rax+18h], rsi
0x18001361b  push    rdi
0x18001361c  sub     rsp, 30h
0x180013620  xor     ebx, ebx
0x180013622  lea     r8, [rax+8]; IsMember
0x180013626  mov     [rcx], ebx
0x180013628  mov     rdi, rcx
0x18001362b  mov     rdx, cs:hMem; SidToCheck
0x180013632  xor     ecx, ecx; TokenHandle
0x180013634  mov     [rax+8], ebx
0x180013637  call    cs:__imp_CheckTokenMembership
0x18001363e  nop     dword ptr [rax+rax+00h]
0x180013643  lea     rsi, WPP_GLOBAL_Control
0x18001364a  test    eax, eax
0x18001364c  jnz     short loc_180013688
0x18001364e  call    cs:__imp_GetLastError
0x180013655  nop     dword ptr [rax+rax+00h]
0x18001365a  mov     ebx, eax
0x18001365c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013663  cmp     rcx, rsi
0x180013666  jz      short loc_1800136C8
0x180013668  test    byte ptr [rcx+1Ch], 1
0x18001366c  jz      short loc_180013695
0x18001366e  mov     rcx, [rcx+10h]
0x180013672  lea     r8, WPP_b3aa15e3641333918320d88489d2b829_Traceguids
0x180013679  mov     edx, 1Ah
0x18001367e  mov     r9d, eax
0x180013681  call    WPP_SF_d
0x180013686  jmp     short loc_18001368E
0x180013688  mov     eax, [rsp+38h+arg_0]
0x18001368c  mov     [rdi], eax
0x18001368e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013695  cmp     rcx, rsi
0x180013698  jz      short loc_1800136C8
0x18001369a  test    byte ptr [rcx+1Ch], 8
0x18001369e  jz      short loc_1800136C8
0x1800136a0  cmp     [rsp+38h+arg_0], 1
0x1800136a5  lea     rdx, aFalse; "FALSE"
0x1800136ac  mov     rcx, [rcx+10h]
0x1800136b0  lea     rax, aTrue; "TRUE"
0x1800136b7  cmovnz  rax, rdx
0x1800136bb  mov     r9d, ebx
0x1800136be  mov     [rsp+38h+var_18], rax
0x1800136c3  call    WPP_SF_ds
0x1800136c8  mov     rbx, [rsp+38h+arg_8]
0x1800136cd  mov     rsi, [rsp+38h+arg_10]
0x1800136d2  add     rsp, 30h
0x1800136d6  pop     rdi
0x1800136d7  retn
```
