# CDRMReader::CreateReaderEvents(ulong)

- ea: `0x18002325c`
- end: `0x1800233f8`
- name: `?CreateReaderEvents@CDRMReader@@QEAAJK@Z`
- size: `412`
- prototype: `__int64 __fastcall(CDRMReader *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001b4b0`

## callees

- `0x180001244`
- `0x180001284`
- `0x180017358`
- `0x18002325c`
- `0x180037b58`
- `0x18005bd72`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800233df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800233df`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023288`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023288`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800233a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800233a4`

## string_xrefs

- `0x180023303`: `UDRMReaderLicAcq_%lu`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDRMReader::CreateReaderEvents(CDRMReader *this, unsigned int a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // r15
  void *v5; // r14
  signed int v6; // ebx
  void *v7; // rsi
  void *v8; // rdi
  struct _SECURITY_ATTRIBUTES *v9; // rdx
  HANDLE EventA; // rax
  struct _SECURITY_ATTRIBUTES *v11; // rdx
  HANDLE v12; // rax
  struct _SECURITY_ATTRIBUTES *v13; // rdx
  HANDLE v14; // rax
  signed int LastError; // eax

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v5 = operator new(0x64u);
  if ( !v5 )
  {
    v6 = -2147024882;
    goto LABEL_19;
  }
  v7 = operator new(0x64u);
  if ( v7 )
  {
    v8 = operator new(0x64u);
    if ( v8 )
    {
      memset_0(v5, 0, 0x64u);
      memset_0(v7, 0, 0x64u);
      memset_0(v8, 0, 0x64u);
      v6 = StringCchPrintfW((unsigned __int16 *)v5, 0x32u, L"UDRMReaderLicAcq_%lu", a2, -2);
      if ( v6 >= 0 )
      {
        EventA = DRMOS::CreateEventA(0, v9, 0, (DRMOS *)v5);
        *((_QWORD *)this + 18) = EventA;
        if ( !EventA
          || (v6 = StringCchPrintfW((unsigned __int16 *)v7, 0x32u, L"LicAcqTermEvent%lu", a2), v6 >= 0)
          && (v6 = StringCchPrintfW((unsigned __int16 *)v8, 0x32u, L"AcqAdvTermEvent%lu", a2), v6 >= 0)
          && ((v12 = DRMOS::CreateEventA(0, v11, (unsigned __int16 **)1, (DRMOS *)v7), (*((_QWORD *)this + 7) = v12) == 0)
           || (v14 = DRMOS::CreateEventA(0, v13, (unsigned __int16 **)1, (DRMOS *)v8), (*((_QWORD *)this + 8) = v14) == 0)) )
        {
          LastError = GetLastError();
          v6 = LastError;
          if ( LastError > 0 )
            v6 = (unsigned __int16)LastError | 0x80070000;
        }
      }
      goto LABEL_15;
    }
  }
  else
  {
    v8 = 0;
  }
  v6 = -2147024882;
LABEL_15:
  operator delete(v5);
  if ( v7 )
    operator delete(v7);
  if ( v8 )
    operator delete(v8);
LABEL_19:
  LeaveCriticalSection(v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002325c  mov     rax, rsp
0x18002325f  push    rbx
0x180023260  push    rbp
0x180023261  push    rsi
0x180023262  push    rdi
0x180023263  push    r12
0x180023265  push    r13
0x180023267  push    r14
0x180023269  push    r15
0x18002326b  sub     rsp, 38h
0x18002326f  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x180023277  mov     r12d, edx
0x18002327a  mov     rbp, rcx
0x18002327d  lea     r15, [rcx+58h]
0x180023281  mov     [rax+8], r15
0x180023285  mov     rcx, r15; lpCriticalSection
0x180023288  call    cs:__imp_EnterCriticalSection
0x18002328e  nop
0x18002328f  mov     ebx, 64h ; 'd'
0x180023294  mov     ecx, ebx; Size
0x180023296  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002329b  mov     r14, rax
0x18002329e  test    rax, rax
0x1800232a1  jnz     short loc_1800232AD
0x1800232a3  mov     ebx, 8007000Eh
0x1800232a8  jmp     loc_1800233DC
0x1800232ad  mov     rcx, rbx; Size
0x1800232b0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800232b5  mov     rsi, rax
0x1800232b8  test    rax, rax
0x1800232bb  jnz     short loc_1800232C9
0x1800232bd  xor     edi, edi
0x1800232bf  mov     ebx, 8007000Eh
0x1800232c4  jmp     loc_1800233B9
0x1800232c9  mov     rcx, rbx; Size
0x1800232cc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800232d1  mov     rdi, rax
0x1800232d4  test    rax, rax
0x1800232d7  jz      short loc_1800232BF
0x1800232d9  mov     r8, rbx; Size
0x1800232dc  xor     edx, edx; Val
0x1800232de  mov     rcx, r14; void *
0x1800232e1  call    memset_0
0x1800232e6  mov     r8, rbx; Size
0x1800232e9  xor     edx, edx; Val
0x1800232eb  mov     rcx, rsi; void *
0x1800232ee  call    memset_0
0x1800232f3  mov     r8, rbx; Size
0x1800232f6  xor     edx, edx; Val
0x1800232f8  mov     rcx, rdi; void *
0x1800232fb  call    memset_0
0x180023300  mov     r9d, r12d
0x180023303  lea     r8, ?g_wszLA_ReaderCancelEventName@@3QBGB; "UDRMReaderLicAcq_%lu"
0x18002330a  mov     r13d, 32h ; '2'
0x180023310  mov     edx, r13d; unsigned __int64
0x180023313  mov     rcx, r14; unsigned __int16 *
0x180023316  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002331b  mov     ebx, eax
0x18002331d  test    eax, eax
0x18002331f  js      loc_1800233B9
0x180023325  mov     r9, r14; int
0x180023328  xor     r8d, r8d; int
0x18002332b  xor     ecx, ecx; lpEventAttributes
0x18002332d  call    ?CreateEventA@DRMOS@@YAPEAXPEAU_SECURITY_ATTRIBUTES@@HHPEBG@Z; DRMOS::CreateEventA(_SECURITY_ATTRIBUTES *,int,int,ushort const *)
0x180023332  mov     [rbp+90h], rax
0x180023339  test    rax, rax
0x18002333c  jz      short loc_1800233A4
0x18002333e  mov     r9d, r12d
0x180023341  lea     r8, aLicacqtermeven; "LicAcqTermEvent%lu"
0x180023348  mov     edx, r13d; unsigned __int64
0x18002334b  mov     rcx, rsi; unsigned __int16 *
0x18002334e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180023353  mov     ebx, eax
0x180023355  test    eax, eax
0x180023357  js      short loc_1800233B9
0x180023359  mov     r9d, r12d
0x18002335c  lea     r8, aAcqadvtermeven; "AcqAdvTermEvent%lu"
0x180023363  mov     edx, r13d; unsigned __int64
0x180023366  mov     rcx, rdi; unsigned __int16 *
0x180023369  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002336e  mov     ebx, eax
0x180023370  test    eax, eax
0x180023372  js      short loc_1800233B9
0x180023374  mov     r9, rsi; int
0x180023377  lea     r12d, [r13-31h]
0x18002337b  mov     r8d, r12d; int
0x18002337e  xor     ecx, ecx; lpEventAttributes
0x180023380  call    ?CreateEventA@DRMOS@@YAPEAXPEAU_SECURITY_ATTRIBUTES@@HHPEBG@Z; DRMOS::CreateEventA(_SECURITY_ATTRIBUTES *,int,int,ushort const *)
0x180023385  mov     [rbp+38h], rax
0x180023389  test    rax, rax
0x18002338c  jz      short loc_1800233A4
0x18002338e  mov     r9, rdi; int
0x180023391  mov     r8d, r12d; int
0x180023394  xor     ecx, ecx; lpEventAttributes
0x180023396  call    ?CreateEventA@DRMOS@@YAPEAXPEAU_SECURITY_ATTRIBUTES@@HHPEBG@Z; DRMOS::CreateEventA(_SECURITY_ATTRIBUTES *,int,int,ushort const *)
0x18002339b  mov     [rbp+40h], rax
0x18002339f  test    rax, rax
0x1800233a2  jnz     short loc_1800233B9
0x1800233a4  call    cs:__imp_GetLastError
0x1800233aa  mov     ebx, eax
0x1800233ac  test    eax, eax
0x1800233ae  jle     short loc_1800233B9
0x1800233b0  movzx   ebx, ax
0x1800233b3  or      ebx, 80070000h
0x1800233b9  mov     rcx, r14; Block
0x1800233bc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800233c1  test    rsi, rsi
0x1800233c4  jz      short loc_1800233CE
0x1800233c6  mov     rcx, rsi; Block
0x1800233c9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800233ce  test    rdi, rdi
0x1800233d1  jz      short loc_1800233DC
0x1800233d3  mov     rcx, rdi; Block
0x1800233d6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800233db  nop
0x1800233dc  mov     rcx, r15; lpCriticalSection
0x1800233df  call    cs:__imp_LeaveCriticalSection
0x1800233e5  mov     eax, ebx
0x1800233e7  add     rsp, 38h
0x1800233eb  pop     r15
0x1800233ed  pop     r14
0x1800233ef  pop     r13
0x1800233f1  pop     r12
0x1800233f3  pop     rdi
0x1800233f4  pop     rsi
0x1800233f5  pop     rbp
0x1800233f6  pop     rbx
0x1800233f7  retn
```
