# SSI_INCLUDE_FILE::DoFLastMod(STRU *)

- ea: `0x180003fac`
- end: `0x1800040e4`
- name: `?DoFLastMod@SSI_INCLUDE_FILE@@AEAAJPEAVSTRU@@@Z`
- size: `312`
- prototype: `signed int __fastcall(SSI_INCLUDE_FILE *this, struct STRU *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180004afc`

## callees

- `0x180002648`
- `0x180003a34`
- `0x180003fac`
- `0x180005780`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040b6`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180004084`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180004084`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180004096`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180004096`

## pseudocode

```c
signed int __fastcall SSI_INCLUDE_FILE::DoFLastMod(SSI_INCLUDE_FILE *this, struct STRU *a2)
{
  unsigned __int16 *v2; // rax
  __int64 v3; // r9
  __int64 v5; // r9
  int v6; // r8d
  int v7; // ecx
  struct SSI_REQUEST *v8; // rcx
  signed int result; // eax
  struct SSI_FILE *v10; // rsi
  int v11; // ebx
  FILETIME FileTime; // [rsp+20h] [rbp-30h] BYREF
  struct SSI_FILE *v13; // [rsp+28h] [rbp-28h] BYREF
  struct _FILETIME LocalFileTime; // [rsp+30h] [rbp-20h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+38h] [rbp-18h] BYREF

  v2 = (unsigned __int16 *)*((_QWORD *)a2 + 4);
  v3 = *((_QWORD *)this + 10);
  SystemTime = 0;
  v5 = v3 - (_QWORD)v2;
  FileTime = 0;
  LocalFileTime = 0;
  do
  {
    v6 = *(unsigned __int16 *)((char *)v2 + v5);
    v7 = *v2 - v6;
    if ( v7 )
      break;
    ++v2;
  }
  while ( v6 );
  if ( v7 )
  {
    v8 = (struct SSI_REQUEST *)*((_QWORD *)this + 2);
    v13 = 0;
    result = SSI_FILE::GetReferencedInstance(v8, a2, &v13);
    if ( result < 0 )
      return result;
    v10 = v13;
    (*(void (__fastcall **)(_QWORD, FILETIME *))(**((_QWORD **)v13 + 2) + 104LL))(*((_QWORD *)v13 + 2), &FileTime);
    v11 = *((_DWORD *)v10 + 10);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v10 + 2) + 16LL))(*((_QWORD *)v10 + 2));
    if ( !v11 )
      (**(void (__fastcall ***)(struct SSI_FILE *))v10)(v10);
  }
  else
  {
    (*(void (__fastcall **)(_QWORD, FILETIME *))(**(_QWORD **)(*((_QWORD *)this + 4) + 16LL) + 104LL))(
      *(_QWORD *)(*((_QWORD *)this + 4) + 16LL),
      &FileTime);
  }
  if ( FileTimeToLocalFileTime(&FileTime, &LocalFileTime) && FileTimeToSystemTime(&LocalFileTime, &SystemTime) )
    return SSI_REQUEST::SendDate(*((SSI_REQUEST **)this + 2), &SystemTime, (SSI_INCLUDE_FILE *)((char *)this + 704));
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180003fac  mov     [rsp-18h+arg_10], rbx
0x180003fb1  push    rbp
0x180003fb2  push    rsi
0x180003fb3  push    rdi
0x180003fb4  mov     rbp, rsp
0x180003fb7  sub     rsp, 50h
0x180003fbb  mov     rax, cs:__security_cookie
0x180003fc2  xor     rax, rsp
0x180003fc5  mov     [rbp+var_8], rax
0x180003fc9  mov     rax, [rdx+20h]
0x180003fcd  xorps   xmm0, xmm0
0x180003fd0  mov     r9, [rcx+50h]
0x180003fd4  mov     rdi, rcx
0x180003fd7  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180003fdb  sub     r9, rax
0x180003fde  mov     qword ptr [rbp+FileTime.dwLowDateTime], 0
0x180003fe6  mov     qword ptr [rbp+LocalFileTime.dwLowDateTime], 0
0x180003fee  movzx   ecx, word ptr [rax]
0x180003ff1  movzx   r8d, word ptr [rax+r9]
0x180003ff6  sub     ecx, r8d
0x180003ff9  jnz     short loc_180004004
0x180003ffb  add     rax, 2
0x180003fff  test    r8d, r8d
0x180004002  jnz     short loc_180003FEE
0x180004004  test    ecx, ecx
0x180004006  jz      short loc_180004064
0x180004008  mov     rcx, [rdi+10h]; struct SSI_REQUEST *
0x18000400c  lea     r8, [rbp+var_28]; struct SSI_FILE **
0x180004010  mov     [rbp+var_28], 0
0x180004018  call    ?GetReferencedInstance@SSI_FILE@@SAJPEAVSSI_REQUEST@@AEAVSTRU@@PEAPEAV1@@Z; SSI_FILE::GetReferencedInstance(SSI_REQUEST *,STRU &,SSI_FILE * *)
0x18000401d  test    eax, eax
0x18000401f  js      loc_1800040C8
0x180004025  mov     rsi, [rbp+var_28]
0x180004029  lea     rdx, [rbp+FileTime]
0x18000402d  mov     rcx, [rsi+10h]
0x180004031  mov     rax, [rcx]
0x180004034  mov     rax, [rax+68h]
0x180004038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000403d  mov     ebx, [rsi+28h]
0x180004040  mov     rcx, [rsi+10h]
0x180004044  mov     rax, [rcx]
0x180004047  mov     rax, [rax+10h]
0x18000404b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004050  test    ebx, ebx
0x180004052  jnz     short loc_18000407C
0x180004054  mov     rax, [rsi]
0x180004057  mov     rcx, rsi
0x18000405a  mov     rax, [rax]
0x18000405d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004062  jmp     short loc_18000407C
0x180004064  mov     rax, [rdi+20h]
0x180004068  lea     rdx, [rbp+FileTime]
0x18000406c  mov     rcx, [rax+10h]
0x180004070  mov     rax, [rcx]
0x180004073  mov     rax, [rax+68h]
0x180004077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000407c  lea     rdx, [rbp+LocalFileTime]; lpLocalFileTime
0x180004080  lea     rcx, [rbp+FileTime]; lpFileTime
0x180004084  call    cs:__imp_FileTimeToLocalFileTime
0x18000408a  test    eax, eax
0x18000408c  jz      short loc_1800040B6
0x18000408e  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x180004092  lea     rcx, [rbp+LocalFileTime]; lpFileTime
0x180004096  call    cs:__imp_FileTimeToSystemTime
0x18000409c  test    eax, eax
0x18000409e  jz      short loc_1800040B6
0x1800040a0  mov     rcx, [rdi+10h]; this
0x1800040a4  lea     r8, [rdi+2C0h]; struct STRA *
0x1800040ab  lea     rdx, [rbp+SystemTime]; struct _SYSTEMTIME *
0x1800040af  call    ?SendDate@SSI_REQUEST@@QEAAJPEAU_SYSTEMTIME@@PEAVSTRA@@@Z; SSI_REQUEST::SendDate(_SYSTEMTIME *,STRA *)
0x1800040b4  jmp     short loc_1800040C8
0x1800040b6  call    cs:__imp_GetLastError
0x1800040bc  test    eax, eax
0x1800040be  jle     short loc_1800040C8
0x1800040c0  movzx   eax, ax
0x1800040c3  or      eax, 80070000h
0x1800040c8  mov     rcx, [rbp+var_8]
0x1800040cc  xor     rcx, rsp; StackCookie
0x1800040cf  call    __security_check_cookie
0x1800040d4  mov     rbx, [rsp+50h+arg_10]
0x1800040dc  add     rsp, 50h
0x1800040e0  pop     rdi
0x1800040e1  pop     rsi
0x1800040e2  pop     rbp
0x1800040e3  retn
```
