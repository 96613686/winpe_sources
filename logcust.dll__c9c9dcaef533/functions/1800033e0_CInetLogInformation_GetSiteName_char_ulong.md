# CInetLogInformation::GetSiteName(char *,ulong *)

- ea: `0x1800033e0`
- end: `0x1800034eb`
- name: `?GetSiteName@CInetLogInformation@@UEAAPEADPEADPEAK@Z`
- size: `267`
- prototype: `char *(CInetLogInformation *__hidden this, char *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x1800033e0`
- `0x180003604`
- `0x1800037d0`
- `0x180004010`

## import_xrefs

- `msvcrt!_ultoa_s` at `0x180003495`
- `msvcrt!_ultoa_s` at `0x180003495`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000344f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000344f`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800034af`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800034af`

## pseudocode

```c
char *__fastcall CInetLogInformation::GetSiteName(CInetLogInformation *this, char *a2, unsigned int *a3)
{
  const char *v6; // r8
  __int64 v7; // rcx
  char *v8; // rdx
  __int64 v9; // rax
  char *v10; // rax
  DWORD v11; // ecx
  char *result; // rax
  __int64 v13; // rax
  unsigned int v14; // eax
  CInetLogInformation *v15; // rcx
  char v16[5]; // [rsp+30h] [rbp-48h] BYREF
  char Buffer[27]; // [rsp+35h] [rbp-43h] BYREF

  v6 = "W3SVC";
  v7 = 32;
  v8 = v16;
  v9 = 2147483646;
  do
  {
    if ( !v9 )
      break;
    if ( !*v6 )
      break;
    *v8++ = *v6++;
    --v9;
    --v7;
  }
  while ( v7 );
  v10 = v8 - 1;
  if ( v7 )
    v10 = v8;
  *v10 = 0;
  if ( !v7 )
  {
    v11 = 122;
LABEL_9:
    SetLastError(v11);
    result = 0;
    *a3 = 0;
    return result;
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD, char *, const char *))(**((_QWORD **)this + 8) + 24LL))(
          *((_QWORD *)this + 8),
          v8,
          v6);
  v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 176LL))(v13);
  if ( _ultoa_s(v14, Buffer, 0x1Bu, 10) )
  {
    v11 = 13;
    goto LABEL_9;
  }
  if ( (int)STRA::Copy((CInetLogInformation *)((char *)this + 72), v16) < 0 )
  {
    v11 = 8;
    goto LABEL_9;
  }
  return CInetLogInformation::ReturnStringInfo(v15, a2, a3, *((const char **)this + 13), *((_DWORD *)this + 30));
}

```

## disassembly

```asm
0x1800033e0  push    rbx
0x1800033e2  push    rsi
0x1800033e3  push    rdi
0x1800033e4  sub     rsp, 60h
0x1800033e8  mov     rax, cs:__security_cookie
0x1800033ef  xor     rax, rsp
0x1800033f2  mov     [rsp+78h+var_28], rax
0x1800033f7  mov     rbx, r8
0x1800033fa  mov     rsi, rdx
0x1800033fd  mov     rdi, rcx
0x180003400  lea     r8, aW3svc; "W3SVC"
0x180003407  mov     ecx, 20h ; ' '
0x18000340c  lea     rdx, [rsp+78h+var_48]
0x180003411  mov     eax, 7FFFFFFEh
0x180003416  test    rax, rax
0x180003419  jz      short loc_180003435
0x18000341b  mov     r9b, [r8]
0x18000341e  test    r9b, r9b
0x180003421  jz      short loc_180003435
0x180003423  mov     [rdx], r9b
0x180003426  inc     r8
0x180003429  inc     rdx
0x18000342c  dec     rax
0x18000342f  sub     rcx, 1
0x180003433  jnz     short loc_180003416
0x180003435  test    rcx, rcx
0x180003438  lea     rax, [rdx-1]
0x18000343c  cmovnz  rax, rdx
0x180003440  mov     byte ptr [rax], 0
0x180003443  jnz     short loc_18000345F
0x180003445  neg     rcx
0x180003448  sbb     ecx, ecx
0x18000344a  not     ecx
0x18000344c  and     ecx, 7Ah; dwErrCode
0x18000344f  call    cs:__imp_SetLastError
0x180003455  xor     eax, eax
0x180003457  mov     dword ptr [rbx], 0
0x18000345d  jmp     short loc_1800034D6
0x18000345f  mov     rcx, [rdi+40h]
0x180003463  mov     rax, [rcx]
0x180003466  mov     rax, [rax+18h]
0x18000346a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000346f  mov     rdx, rax
0x180003472  mov     rcx, [rax]
0x180003475  mov     rax, [rcx+0B0h]
0x18000347c  mov     rcx, rdx
0x18000347f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003484  mov     r9d, 0Ah; Radix
0x18000348a  lea     rdx, [rsp+78h+Buffer]; Buffer
0x18000348f  mov     ecx, eax; Value
0x180003491  lea     r8d, [r9+11h]; BufferCount
0x180003495  call    cs:__imp__ultoa_s
0x18000349b  test    eax, eax
0x18000349d  jz      short loc_1800034A6
0x18000349f  mov     ecx, 0Dh
0x1800034a4  jmp     short loc_18000344F
0x1800034a6  lea     rcx, [rdi+48h]
0x1800034aa  lea     rdx, [rsp+78h+var_48]
0x1800034af  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x1800034b5  test    eax, eax
0x1800034b7  jns     short loc_1800034C0
0x1800034b9  mov     ecx, 8
0x1800034be  jmp     short loc_18000344F
0x1800034c0  mov     eax, [rdi+78h]
0x1800034c3  mov     r8, rbx; unsigned int *
0x1800034c6  mov     r9, [rdi+68h]; char *
0x1800034ca  mov     rdx, rsi; char *
0x1800034cd  mov     [rsp+78h+var_58], eax; unsigned int
0x1800034d1  call    ?ReturnStringInfo@CInetLogInformation@@AEAAPEADPEADPEAKPEBDK@Z; CInetLogInformation::ReturnStringInfo(char *,ulong *,char const *,ulong)
0x1800034d6  mov     rcx, [rsp+78h+var_28]
0x1800034db  xor     rcx, rsp; StackCookie
0x1800034de  call    __security_check_cookie
0x1800034e3  add     rsp, 60h
0x1800034e7  pop     rdi
0x1800034e8  pop     rsi
0x1800034e9  pop     rbx
0x1800034ea  retn
```
