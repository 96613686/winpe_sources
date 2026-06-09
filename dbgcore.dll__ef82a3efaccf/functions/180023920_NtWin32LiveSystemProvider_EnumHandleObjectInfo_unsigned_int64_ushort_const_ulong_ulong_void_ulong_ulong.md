# NtWin32LiveSystemProvider::EnumHandleObjectInfo(unsigned __int64,ushort const *,ulong,ulong *,void *,ulong,ulong *)

- ea: `0x180023920`
- end: `0x180023db1`
- name: `?EnumHandleObjectInfo@NtWin32LiveSystemProvider@@UEAAJ_KPEBGKPEAKPEAXK2@Z`
- size: `1169`
- prototype: `__int64 __usercall@<rax>(NtWin32LiveSystemProvider *__hidden this@<rcx>, unsigned __int64@<rdx>, LPCWSTR lpString1@<r8>, unsigned int@<r9d>, unsigned int *, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180023398`
- `0x180023920`
- `0x180026ef4`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023b02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023b0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023b02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023b0c`
- `api-ms-win-core-misc-l1-1-0!lstrcmpiW` at `0x180023958`
- `api-ms-win-core-misc-l1-1-0!lstrcmpiW` at `0x180023a41`
- `api-ms-win-core-misc-l1-1-0!lstrcmpiW` at `0x180023ac7`
- `api-ms-win-core-misc-l1-1-0!lstrcmpiW` at `0x180023bc9`
- `api-ms-win-core-misc-l1-1-0!lstrcmpiW` at `0x180023c5b`
- `api-ms-win-core-misc-l1-1-0!lstrcmpiW` at `0x180023d10`
- `api-ms-win-core-misc-l1-1-0!lstrcmpiW` at `0x180023958`
- `api-ms-win-core-misc-l1-1-0!lstrcmpiW` at `0x180023a41`
- `api-ms-win-core-misc-l1-1-0!lstrcmpiW` at `0x180023ac7`
- `api-ms-win-core-misc-l1-1-0!lstrcmpiW` at `0x180023bc9`
- `api-ms-win-core-misc-l1-1-0!lstrcmpiW` at `0x180023c5b`
- `api-ms-win-core-misc-l1-1-0!lstrcmpiW` at `0x180023d10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023d95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023d95`

## string_xrefs

- `0x180023a37`: `Thread`

## pseudocode

```c
signed int __fastcall NtWin32LiveSystemProvider::EnumHandleObjectInfo(
        NtWin32LiveSystemProvider *this,
        unsigned __int64 a2,
        LPCWSTR lpString1,
        unsigned int a4,
        unsigned int *a5,
        _QWORD *a6,
        unsigned int a7,
        unsigned int *a8)
{
  signed int result; // eax
  int v13; // ebx
  int InformationThread; // eax
  unsigned int v15; // esi
  MiniDumpOsImports *v16; // rcx
  unsigned int v17; // r9d
  HANDLE v18; // rcx
  unsigned int v19; // esi
  __int64 v20; // r9
  __int64 v21; // r9
  HANDLE hObject; // [rsp+30h] [rbp-10h] BYREF
  __int64 v23; // [rsp+38h] [rbp-8h] BYREF

  hObject = 0;
  v23 = 0;
  if ( !lstrcmpiW(lpString1, L"Mutant") )
  {
    if ( *((_QWORD *)this + 109) && a4 < 3 )
    {
      result = NtWin32LiveSystemProvider::DupSame(this, a2, &hObject);
      v13 = result;
      if ( result )
        return result;
      if ( !a4 )
      {
        v15 = 8;
        if ( a7 < 8 )
          v15 = a7;
        InformationThread = (*((__int64 (__fastcall **)(HANDLE, _QWORD, _QWORD *, _QWORD, unsigned int *))this + 109))(
                              hObject,
                              0,
                              a6,
                              v15,
                              a8);
        if ( InformationThread >= 0 )
        {
          *a5 = 2;
          goto LABEL_66;
        }
        goto LABEL_64;
      }
      if ( a4 == 2 )
      {
        InformationThread = (*((__int64 (__fastcall **)(HANDLE, __int64, _QWORD *))this + 109))(hObject, 1, a6);
        if ( InformationThread >= 0 )
        {
          *a5 = 3;
          goto LABEL_66;
        }
        goto LABEL_64;
      }
      goto LABEL_60;
    }
    return 1;
  }
  if ( !lstrcmpiW(lpString1, L"Thread") )
  {
    if ( g_NtDllCallsMdwd && !a4 )
    {
      result = NtWin32LiveSystemProvider::DupSame(this, a2, &hObject);
      v13 = result;
      if ( result )
        return result;
      v17 = 48;
      if ( a7 < 0x30 )
        v17 = a7;
      InformationThread = MiniDumpOsImports::NtQueryInformationThread(v16, hObject, ThreadBasicInformation, a6, v17, a8);
      if ( InformationThread >= 0 )
      {
        *a5 = 1;
        goto LABEL_66;
      }
      goto LABEL_64;
    }
    return 1;
  }
  if ( lstrcmpiW(lpString1, L"Process") )
  {
    if ( lstrcmpiW(lpString1, L"Event") )
    {
      if ( lstrcmpiW(lpString1, L"Section") )
      {
        if ( !lstrcmpiW(lpString1, L"Semaphore") && *((_QWORD *)this + 110) && a4 < 8 )
        {
          result = NtWin32LiveSystemProvider::DupSame(this, a2, &hObject);
          v13 = result;
          if ( result )
            return result;
          if ( !a4 )
          {
            v21 = a7;
            if ( a7 >= 8 )
              v21 = 8;
            InformationThread = (*((__int64 (__fastcall **)(HANDLE, _QWORD, _QWORD *, __int64, unsigned int *))this + 110))(
                                  hObject,
                                  0,
                                  a6,
                                  v21,
                                  a8);
            if ( InformationThread >= 0 )
            {
              *a5 = 8;
              goto LABEL_66;
            }
            goto LABEL_64;
          }
          goto LABEL_60;
        }
      }
      else if ( *((_QWORD *)this + 122) && a4 < 7 )
      {
        result = NtWin32LiveSystemProvider::DupSame(this, a2, &hObject);
        v13 = result;
        if ( result )
          return result;
        if ( !a4 )
        {
          v20 = 24;
          if ( a7 < 0x18 )
            v20 = a7;
          InformationThread = (*((__int64 (__fastcall **)(HANDLE, _QWORD, _QWORD *, __int64, __int64 *))this + 122))(
                                hObject,
                                0,
                                a6,
                                v20,
                                &v23);
          if ( InformationThread >= 0 )
          {
            if ( HIDWORD(v23) )
            {
              v13 = -2147024785;
            }
            else
            {
              *a8 = v23;
              *a5 = 7;
            }
LABEL_66:
            if ( hObject )
              CloseHandle(hObject);
            return v13;
          }
LABEL_64:
          v13 = InformationThread | 0x10000000;
          goto LABEL_66;
        }
LABEL_60:
        v13 = 1;
        goto LABEL_66;
      }
    }
    else if ( *((_QWORD *)this + 121) && a4 < 6 )
    {
      result = NtWin32LiveSystemProvider::DupSame(this, a2, &hObject);
      v13 = result;
      if ( result )
        return result;
      if ( !a4 )
      {
        v19 = 8;
        if ( a7 < 8 )
          v19 = a7;
        InformationThread = (*((__int64 (__fastcall **)(HANDLE, _QWORD, _QWORD *, _QWORD, unsigned int *))this + 121))(
                              hObject,
                              0,
                              a6,
                              v19,
                              a8);
        if ( InformationThread >= 0 )
        {
          *a5 = 6;
          goto LABEL_66;
        }
        goto LABEL_64;
      }
      goto LABEL_60;
    }
    return 1;
  }
  if ( !*((_QWORD *)this + 107) || a4 >= 4 )
    return 1;
  v13 = NtWin32LiveSystemProvider::DupSame(this, a2, &hObject);
  if ( !v13 )
  {
    if ( !a4 )
    {
      if ( a7 >= 0x40 )
      {
        v18 = hObject;
        *a6 = 64;
        if ( (*((int (__fastcall **)(HANDLE, _QWORD, _QWORD *))this + 107))(v18, 0, a6) >= 0 )
        {
          *a5 = 5;
          goto LABEL_66;
        }
      }
      InformationThread = (*((__int64 (__fastcall **)(HANDLE, _QWORD, _QWORD *))this + 107))(hObject, 0, a6);
      if ( InformationThread >= 0 )
      {
        *a5 = 4;
        goto LABEL_66;
      }
      goto LABEL_64;
    }
    goto LABEL_60;
  }
  if ( !GetLastError() )
    return -2147467259;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180023920  push    rbp
0x180023922  push    rbx
0x180023923  push    rsi
0x180023924  push    rdi
0x180023925  push    r13
0x180023927  push    r14
0x180023929  push    r15
0x18002392b  mov     rbp, rsp
0x18002392e  sub     rsp, 40h
0x180023932  mov     r15, rdx
0x180023935  mov     [rbp+hObject], 0
0x18002393d  mov     rdi, rcx
0x180023940  mov     [rbp+var_8], 0
0x180023948  lea     rdx, String2; "Mutant"
0x18002394f  mov     rcx, r8; lpString1
0x180023952  mov     r14d, r9d
0x180023955  mov     rbx, r8
0x180023958  call    cs:__imp_lstrcmpiW
0x18002395e  mov     r13d, 1
0x180023964  test    eax, eax
0x180023966  jnz     loc_180023A37
0x18002396c  cmp     qword ptr [rdi+368h], 0
0x180023974  jz      loc_180023D9F
0x18002397a  cmp     r14d, 3
0x18002397e  jnb     loc_180023D9F
0x180023984  lea     r8, [rbp+hObject]; void **
0x180023988  mov     rdx, r15; unsigned __int64
0x18002398b  mov     rcx, rdi; this
0x18002398e  call    ?DupSame@NtWin32LiveSystemProvider@@AEAAJ_KPEAPEAX@Z; NtWin32LiveSystemProvider::DupSame(unsigned __int64,void * *)
0x180023993  mov     ebx, eax
0x180023995  test    eax, eax
0x180023997  jnz     loc_180023DA2
0x18002399d  test    r14d, r14d
0x1800239a0  jz      short loc_1800239F1
0x1800239a2  cmp     r14d, 2
0x1800239a6  jnz     loc_180023D4A
0x1800239ac  lea     r9d, [r13+0Fh]
0x1800239b0  cmp     [rbp+arg_30], r9d
0x1800239b4  jnb     short loc_1800239BA
0x1800239b6  mov     r9d, [rbp+arg_30]
0x1800239ba  mov     rcx, [rbp+arg_38]
0x1800239be  mov     edx, r13d
0x1800239c1  mov     r8, [rbp+arg_28]
0x1800239c5  mov     rax, [rdi+368h]
0x1800239cc  mov     qword ptr [rsp+40h+var_20], rcx
0x1800239d1  mov     rcx, [rbp+hObject]
0x1800239d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800239da  test    eax, eax
0x1800239dc  js      loc_180023D7E
0x1800239e2  mov     rax, [rbp+arg_20]
0x1800239e6  mov     dword ptr [rax], 3
0x1800239ec  jmp     loc_180023D8C
0x1800239f1  mov     esi, 8
0x1800239f6  cmp     [rbp+arg_30], esi
0x1800239f9  jnb     short loc_1800239FE
0x1800239fb  mov     esi, [rbp+arg_30]
0x1800239fe  mov     rcx, [rbp+arg_38]
0x180023a02  mov     r9d, esi
0x180023a05  mov     r8, [rbp+arg_28]
0x180023a09  xor     edx, edx
0x180023a0b  mov     rax, [rdi+368h]
0x180023a12  mov     qword ptr [rsp+40h+var_20], rcx
0x180023a17  mov     rcx, [rbp+hObject]
0x180023a1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a20  test    eax, eax
0x180023a22  js      loc_180023D7E
0x180023a28  mov     rax, [rbp+arg_20]
0x180023a2c  mov     dword ptr [rax], 2
0x180023a32  jmp     loc_180023D8C
0x180023a37  lea     rdx, aThread; "Thread"
0x180023a3e  mov     rcx, rbx; lpString1
0x180023a41  call    cs:__imp_lstrcmpiW
0x180023a47  test    eax, eax
0x180023a49  jnz     short loc_180023ABD
0x180023a4b  mov     rax, qword ptr cs:?g_NtDllCallsMdwd@@3UNTDLL_CALLS_MDWD@@C; NTDLL_CALLS_MDWD volatile g_NtDllCallsMdwd
0x180023a52  test    rax, rax
0x180023a55  jz      loc_180023D9F
0x180023a5b  cmp     r14d, r13d
0x180023a5e  jnb     loc_180023D9F
0x180023a64  lea     r8, [rbp+hObject]; void **
0x180023a68  mov     rdx, r15; unsigned __int64
0x180023a6b  mov     rcx, rdi; this
0x180023a6e  call    ?DupSame@NtWin32LiveSystemProvider@@AEAAJ_KPEAPEAX@Z; NtWin32LiveSystemProvider::DupSame(unsigned __int64,void * *)
0x180023a73  mov     ebx, eax
0x180023a75  test    eax, eax
0x180023a77  jnz     loc_180023DA2
0x180023a7d  lea     r9d, [rax+30h]
0x180023a81  cmp     [rbp+arg_30], r9d
0x180023a85  jnb     short loc_180023A8B
0x180023a87  mov     r9d, [rbp+arg_30]
0x180023a8b  mov     rax, [rbp+arg_38]
0x180023a8f  xor     r8d, r8d; enum _THREADINFOCLASS
0x180023a92  mov     rdx, [rbp+hObject]; void *
0x180023a96  mov     [rsp+40h+var_18], rax; unsigned int *
0x180023a9b  mov     [rsp+40h+var_20], r9d; unsigned int
0x180023aa0  mov     r9, [rbp+arg_28]; void *
0x180023aa4  call    ?NtQueryInformationThread@MiniDumpOsImports@@QEAAJPEAXW4_THREADINFOCLASS@@0KPEAK@Z; MiniDumpOsImports::NtQueryInformationThread(void *,_THREADINFOCLASS,void *,ulong,ulong *)
0x180023aa9  test    eax, eax
0x180023aab  js      loc_180023D7E
0x180023ab1  mov     rax, [rbp+arg_20]
0x180023ab5  mov     [rax], r13d
0x180023ab8  jmp     loc_180023D8C
0x180023abd  lea     rdx, aProcess; "Process"
0x180023ac4  mov     rcx, rbx; lpString1
0x180023ac7  call    cs:__imp_lstrcmpiW
0x180023acd  test    eax, eax
0x180023acf  jnz     loc_180023BBF
0x180023ad5  cmp     qword ptr [rdi+358h], 0
0x180023add  jz      loc_180023D9F
0x180023ae3  cmp     r14d, 4
0x180023ae7  jnb     loc_180023D9F
0x180023aed  lea     r8, [rbp+hObject]; void **
0x180023af1  mov     rdx, r15; unsigned __int64
0x180023af4  mov     rcx, rdi; this
0x180023af7  call    ?DupSame@NtWin32LiveSystemProvider@@AEAAJ_KPEAPEAX@Z; NtWin32LiveSystemProvider::DupSame(unsigned __int64,void * *)
0x180023afc  mov     ebx, eax
0x180023afe  test    eax, eax
0x180023b00  jz      short loc_180023B31
0x180023b02  call    cs:__imp_GetLastError
0x180023b08  test    eax, eax
0x180023b0a  jz      short loc_180023B27
0x180023b0c  call    cs:__imp_GetLastError
0x180023b12  test    eax, eax
0x180023b14  jle     loc_180023DA2
0x180023b1a  movzx   eax, ax
0x180023b1d  or      eax, 80070000h
0x180023b22  jmp     loc_180023DA2
0x180023b27  mov     eax, 80004005h
0x180023b2c  jmp     loc_180023DA2
0x180023b31  test    r14d, r14d
0x180023b34  jnz     loc_180023D4A
0x180023b3a  mov     esi, [rbp+arg_30]
0x180023b3d  mov     r9d, 40h ; '@'
0x180023b43  mov     r15, [rbp+arg_38]
0x180023b47  mov     r14, [rbp+arg_28]
0x180023b4b  cmp     esi, r9d
0x180023b4e  jb      short loc_180023B80
0x180023b50  mov     rcx, [rbp+hObject]
0x180023b54  mov     r8, r14
0x180023b57  mov     [r14], r9
0x180023b5a  xor     edx, edx
0x180023b5c  mov     rax, [rdi+358h]
0x180023b63  mov     qword ptr [rsp+40h+var_20], r15
0x180023b68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b6d  test    eax, eax
0x180023b6f  js      short loc_180023B80
0x180023b71  mov     rax, [rbp+arg_20]
0x180023b75  mov     dword ptr [rax], 5
0x180023b7b  jmp     loc_180023D8C
0x180023b80  mov     r9d, 30h ; '0'
0x180023b86  cmp     esi, r9d
0x180023b89  jnb     short loc_180023B8E
0x180023b8b  mov     r9, rsi
0x180023b8e  mov     rcx, [rbp+hObject]
0x180023b92  mov     r8, r14
0x180023b95  mov     rax, [rdi+358h]
0x180023b9c  xor     edx, edx
0x180023b9e  mov     qword ptr [rsp+40h+var_20], r15
0x180023ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ba8  test    eax, eax
0x180023baa  js      loc_180023D7E
0x180023bb0  mov     rax, [rbp+arg_20]
0x180023bb4  mov     dword ptr [rax], 4
0x180023bba  jmp     loc_180023D8C
0x180023bbf  lea     rdx, aEvent; "Event"
0x180023bc6  mov     rcx, rbx; lpString1
0x180023bc9  call    cs:__imp_lstrcmpiW
0x180023bcf  test    eax, eax
0x180023bd1  jnz     short loc_180023C51
0x180023bd3  cmp     qword ptr [rdi+3C8h], 0
0x180023bdb  jz      loc_180023D9F
0x180023be1  cmp     r14d, 6
0x180023be5  jnb     loc_180023D9F
0x180023beb  lea     r8, [rbp+hObject]; void **
0x180023bef  mov     rdx, r15; unsigned __int64
0x180023bf2  mov     rcx, rdi; this
0x180023bf5  call    ?DupSame@NtWin32LiveSystemProvider@@AEAAJ_KPEAPEAX@Z; NtWin32LiveSystemProvider::DupSame(unsigned __int64,void * *)
0x180023bfa  mov     ebx, eax
0x180023bfc  test    eax, eax
0x180023bfe  jnz     loc_180023DA2
0x180023c04  test    r14d, r14d
0x180023c07  jnz     loc_180023D4A
0x180023c0d  lea     esi, [rax+8]
0x180023c10  cmp     [rbp+arg_30], esi
0x180023c13  jnb     short loc_180023C18
0x180023c15  mov     esi, [rbp+arg_30]
0x180023c18  mov     rcx, [rbp+arg_38]
0x180023c1c  mov     r9d, esi
0x180023c1f  mov     r8, [rbp+arg_28]
0x180023c23  xor     edx, edx
0x180023c25  mov     rax, [rdi+3C8h]
0x180023c2c  mov     qword ptr [rsp+40h+var_20], rcx
0x180023c31  mov     rcx, [rbp+hObject]
0x180023c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c3a  test    eax, eax
0x180023c3c  js      loc_180023D7E
0x180023c42  mov     rax, [rbp+arg_20]
0x180023c46  mov     dword ptr [rax], 6
0x180023c4c  jmp     loc_180023D8C
0x180023c51  lea     rdx, aSection; "Section"
0x180023c58  mov     rcx, rbx; lpString1
0x180023c5b  call    cs:__imp_lstrcmpiW
0x180023c61  test    eax, eax
0x180023c63  jnz     loc_180023D06
0x180023c69  cmp     qword ptr [rdi+3D0h], 0
0x180023c71  jz      loc_180023D9F
0x180023c77  cmp     r14d, 7
0x180023c7b  jnb     loc_180023D9F
0x180023c81  lea     r8, [rbp+hObject]; void **
0x180023c85  mov     rdx, r15; unsigned __int64
0x180023c88  mov     rcx, rdi; this
0x180023c8b  call    ?DupSame@NtWin32LiveSystemProvider@@AEAAJ_KPEAPEAX@Z; NtWin32LiveSystemProvider::DupSame(unsigned __int64,void * *)
0x180023c90  mov     ebx, eax
0x180023c92  test    eax, eax
0x180023c94  jnz     loc_180023DA2
0x180023c9a  test    r14d, r14d
0x180023c9d  jnz     loc_180023D4A
0x180023ca3  lea     r9d, [rax+18h]
0x180023ca7  cmp     [rbp+arg_30], r9d
0x180023cab  jnb     short loc_180023CB1
0x180023cad  mov     r9d, [rbp+arg_30]
0x180023cb1  mov     r8, [rbp+arg_28]
0x180023cb5  lea     rax, [rbp+var_8]
0x180023cb9  mov     rcx, [rbp+hObject]
0x180023cbd  xor     edx, edx
0x180023cbf  mov     qword ptr [rsp+40h+var_20], rax
0x180023cc4  mov     rax, [rdi+3D0h]
0x180023ccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023cd0  test    eax, eax
0x180023cd2  js      loc_180023D7E
0x180023cd8  mov     rcx, [rbp+var_8]
0x180023cdc  mov     rax, rcx
0x180023cdf  shr     rax, 20h
0x180023ce3  test    eax, eax
0x180023ce5  jz      short loc_180023CF1
0x180023ce7  mov     ebx, 8007006Fh
0x180023cec  jmp     loc_180023D8C
0x180023cf1  mov     rax, [rbp+arg_38]
0x180023cf5  mov     [rax], ecx
0x180023cf7  mov     rax, [rbp+arg_20]
0x180023cfb  mov     dword ptr [rax], 7
0x180023d01  jmp     loc_180023D8C
0x180023d06  lea     rdx, aSemaphore; "Semaphore"
0x180023d0d  mov     rcx, rbx; lpString1
0x180023d10  call    cs:__imp_lstrcmpiW
0x180023d16  test    eax, eax
0x180023d18  jnz     loc_180023D9F
0x180023d1e  cmp     qword ptr [rdi+370h], 0
0x180023d26  jz      short loc_180023D9F
0x180023d28  lea     esi, [rax+8]
0x180023d2b  cmp     r14d, esi
0x180023d2e  jnb     short loc_180023D9F
0x180023d30  lea     r8, [rbp+hObject]; void **
0x180023d34  mov     rdx, r15; unsigned __int64
0x180023d37  mov     rcx, rdi; this
0x180023d3a  call    ?DupSame@NtWin32LiveSystemProvider@@AEAAJ_KPEAPEAX@Z; NtWin32LiveSystemProvider::DupSame(unsigned __int64,void * *)
0x180023d3f  mov     ebx, eax
0x180023d41  test    eax, eax
0x180023d43  jnz     short loc_180023DA2
0x180023d45  test    r14d, r14d
0x180023d48  jz      short loc_180023D4F
0x180023d4a  mov     ebx, r13d
0x180023d4d  jmp     short loc_180023D8C
0x180023d4f  mov     r9d, [rbp+arg_30]
0x180023d53  cmp     [rbp+arg_30], esi
0x180023d56  jb      short loc_180023D5B
0x180023d58  mov     r9, rsi
0x180023d5b  mov     rcx, [rbp+arg_38]
0x180023d5f  xor     edx, edx
0x180023d61  mov     r8, [rbp+arg_28]
0x180023d65  mov     rax, [rdi+370h]
0x180023d6c  mov     qword ptr [rsp+40h+var_20], rcx
0x180023d71  mov     rcx, [rbp+hObject]
0x180023d75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d7a  test    eax, eax
0x180023d7c  jns     short loc_180023D86
0x180023d7e  mov     ebx, eax
0x180023d80  bts     ebx, 1Ch
0x180023d84  jmp     short loc_180023D8C
0x180023d86  mov     rax, [rbp+arg_20]
0x180023d8a  mov     [rax], esi
0x180023d8c  mov     rcx, [rbp+hObject]; hObject
0x180023d90  test    rcx, rcx
0x180023d93  jz      short loc_180023D9B
0x180023d95  call    cs:__imp_CloseHandle
0x180023d9b  mov     eax, ebx
0x180023d9d  jmp     short loc_180023DA2
0x180023d9f  mov     eax, r13d
0x180023da2  add     rsp, 40h
0x180023da6  pop     r15
0x180023da8  pop     r14
0x180023daa  pop     r13
0x180023dac  pop     rdi
0x180023dad  pop     rsi
0x180023dae  pop     rbx
0x180023daf  pop     rbp
0x180023db0  retn
```
