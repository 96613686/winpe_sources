# HrSaveAttachToFile

- ea: `0x18008ed30`
- end: `0x18008ef25`
- name: `HrSaveAttachToFile`
- size: `501`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18008dfb8`
- `0x18008ef30`
- `0x1800cc62c`

## callees

- `0x180005748`
- `0x18008ed30`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!HrCopyStream` at `0x18008eef2`
- `MSOERT2!HrCopyStream` at `0x18008eef2`
- `MSOERT2!OpenFileStreamW` at `0x18008edab`
- `MSOERT2!OpenFileStreamW` at `0x18008edab`
- `MSOERT2!HrIsStreamUnicode` at `0x18008eddb`
- `MSOERT2!HrIsStreamUnicode` at `0x18008eddb`
- `MSOERT2!HrRewindStream` at `0x18008eeb5`
- `MSOERT2!HrRewindStream` at `0x18008eeb5`
- `SHLWAPI!PathIsContentTypeW` at `0x18008edc5`
- `SHLWAPI!PathIsContentTypeW` at `0x18008edc5`

## pseudocode

```c
__int64 __fastcall HrSaveAttachToFile(__int64 a1, __int64 a2, const WCHAR *a3)
{
  int v4; // ebx
  bool v5; // zf
  __int64 (__fastcall *v6)(__int64, char *, __int64, unsigned int *); // rax
  __int64 v7; // r8
  const char *v8; // rdx
  bool v9; // cf
  int v10; // eax
  int v11; // eax
  unsigned int v13; // [rsp+30h] [rbp-20h] BYREF
  int v14; // [rsp+34h] [rbp-1Ch] BYREF
  __int64 v15; // [rsp+38h] [rbp-18h] BYREF
  _QWORD v16[2]; // [rsp+40h] [rbp-10h] BYREF
  char v17; // [rsp+60h] [rbp+10h] BYREF
  unsigned __int8 v18; // [rsp+78h] [rbp+28h] BYREF
  unsigned __int8 v19; // [rsp+79h] [rbp+29h]
  unsigned __int8 v20; // [rsp+7Ah] [rbp+2Ah]

  v15 = 0;
  v16[0] = 0;
  v14 = 0;
  v13 = 0;
  if ( !a1 || !a2 )
  {
    v4 = -2147024809;
    goto LABEL_25;
  }
  v4 = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, __int64 *))(*(_QWORD *)a1 + 128LL))(
         a1,
         a2,
         &IID_IStream,
         &v15);
  if ( v4 >= 0 )
  {
    v4 = OpenFileStreamW(a3, 2, 0x40000000, v16);
    if ( v4 >= 0 )
    {
      if ( !PathIsContentTypeW(a3, L"text/html") )
      {
LABEL_23:
        v4 = HrCopyStream(v15, v16[0], 0);
        goto LABEL_25;
      }
      v5 = (unsigned int)HrIsStreamUnicode(v15, &v14) == 0;
      v6 = *(__int64 (__fastcall **)(__int64, char *, __int64, unsigned int *))(*(_QWORD *)v15 + 24LL);
      if ( v5 )
      {
        v4 = v6(v15, &v17, 2, &v13);
        if ( v4 < 0 )
          goto LABEL_25;
        v4 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, _QWORD))(*(_QWORD *)v16[0] + 32LL))(
               v16[0],
               &v17,
               v13,
               0);
        if ( v4 < 0 )
          goto LABEL_25;
        v7 = 108;
        v8 = (const char *)L"<!-- saved from url=(0022)http://internet.e-mail -->\r\n";
      }
      else
      {
        v4 = v6(v15, (char *)&v18, 3, &v13);
        if ( v4 < 0 )
          goto LABEL_25;
        if ( v13 != 3
          || ((v9 = v18 > 0xEFu, v18 != 0xEF) || (v9 = v19 > 0xBBu, v19 != 0xBB) || (v9 = v20 > 0xBFu, v20 != 0xBF)
            ? (v10 = v9 ? -1 : 1)
            : (v10 = 0),
              v10) )
        {
          v11 = HrRewindStream(v15);
        }
        else
        {
          v11 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64, _QWORD))(*(_QWORD *)v16[0] + 32LL))(
                  v16[0],
                  &byte_1800DDC84,
                  3,
                  0);
        }
        v4 = v11;
        if ( v11 < 0 )
          goto LABEL_25;
        v7 = 54;
        v8 = "<!-- saved from url=(0022)http://internet.e-mail -->\r\n";
      }
      v4 = (*(__int64 (__fastcall **)(_QWORD, const char *, __int64, _QWORD))(*(_QWORD *)v16[0] + 32LL))(
             v16[0],
             v8,
             v7,
             0);
      if ( v4 >= 0 )
        goto LABEL_23;
    }
  }
LABEL_25:
  OE_SafeReleaseAndNullPtr<IStream>(&v15);
  OE_SafeReleaseAndNullPtr<IStream>(v16);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18008ed30  mov     [rsp-8+arg_8], rbx
0x18008ed35  mov     [rsp-8+arg_10], rdi
0x18008ed3a  push    rbp
0x18008ed3b  mov     rbp, rsp
0x18008ed3e  sub     rsp, 50h
0x18008ed42  mov     [rbp+var_18], 0
0x18008ed4a  mov     rdi, r8
0x18008ed4d  mov     [rbp+var_10], 0
0x18008ed55  mov     [rbp+var_1C], 0
0x18008ed5c  mov     [rbp+var_20], 0
0x18008ed63  test    rcx, rcx
0x18008ed66  jz      loc_18008EEFC
0x18008ed6c  test    rdx, rdx
0x18008ed6f  jz      loc_18008EEFC
0x18008ed75  mov     rax, [rcx]
0x18008ed78  lea     r9, [rbp+var_18]
0x18008ed7c  lea     r8, IID_IStream
0x18008ed83  mov     rax, [rax+80h]
0x18008ed8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ed8f  mov     ebx, eax
0x18008ed91  test    eax, eax
0x18008ed93  js      loc_18008EF01
0x18008ed99  lea     r9, [rbp+var_10]
0x18008ed9d  mov     edx, 2
0x18008eda2  mov     r8d, 40000000h
0x18008eda8  mov     rcx, rdi
0x18008edab  call    cs:__imp_OpenFileStreamW
0x18008edb1  mov     ebx, eax
0x18008edb3  test    eax, eax
0x18008edb5  js      loc_18008EF01
0x18008edbb  lea     rdx, pszContentType; "text/html"
0x18008edc2  mov     rcx, rdi; pszPath
0x18008edc5  call    cs:__imp_PathIsContentTypeW
0x18008edcb  test    eax, eax
0x18008edcd  jz      loc_18008EEE7
0x18008edd3  mov     rcx, [rbp+var_18]
0x18008edd7  lea     rdx, [rbp+var_1C]
0x18008eddb  call    cs:__imp_HrIsStreamUnicode
0x18008ede1  mov     rcx, [rbp+var_18]
0x18008ede5  lea     r9, [rbp+var_20]
0x18008ede9  test    eax, eax
0x18008edeb  mov     rax, [rcx]
0x18008edee  mov     rax, [rax+18h]
0x18008edf2  jnz     short loc_18008EE44
0x18008edf4  mov     r8d, 2
0x18008edfa  lea     rdx, [rbp+arg_0]
0x18008edfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ee03  mov     ebx, eax
0x18008ee05  test    eax, eax
0x18008ee07  js      loc_18008EF01
0x18008ee0d  mov     rcx, [rbp+var_10]
0x18008ee11  lea     rdx, [rbp+arg_0]
0x18008ee15  mov     r8d, [rbp+var_20]
0x18008ee19  xor     r9d, r9d
0x18008ee1c  mov     rax, [rcx]
0x18008ee1f  mov     rax, [rax+20h]
0x18008ee23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ee28  mov     ebx, eax
0x18008ee2a  test    eax, eax
0x18008ee2c  js      loc_18008EF01
0x18008ee32  mov     r8d, 6Ch ; 'l'
0x18008ee38  lea     rdx, aSavedFromUrl00; "<!-- saved from url=(0022)http://intern"...
0x18008ee3f  jmp     loc_18008EECE
0x18008ee44  mov     edi, 3
0x18008ee49  lea     rdx, [rbp+arg_18]
0x18008ee4d  mov     r8d, edi
0x18008ee50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ee55  mov     ebx, eax
0x18008ee57  test    eax, eax
0x18008ee59  js      loc_18008EF01
0x18008ee5f  cmp     [rbp+var_20], edi
0x18008ee62  jnz     short loc_18008EEB1
0x18008ee64  mov     al, cs:byte_1800DDC84
0x18008ee6a  cmp     al, [rbp+arg_18]
0x18008ee6d  jnz     short loc_18008EE89
0x18008ee6f  mov     al, cs:byte_1800DDC85
0x18008ee75  cmp     al, [rbp+arg_19]
0x18008ee78  jnz     short loc_18008EE89
0x18008ee7a  mov     al, cs:byte_1800DDC86
0x18008ee80  cmp     al, [rbp+arg_1A]
0x18008ee83  jnz     short loc_18008EE89
0x18008ee85  xor     eax, eax
0x18008ee87  jmp     short loc_18008EE8E
0x18008ee89  sbb     eax, eax
0x18008ee8b  or      eax, 1
0x18008ee8e  test    eax, eax
0x18008ee90  jnz     short loc_18008EEB1
0x18008ee92  mov     rcx, [rbp+var_10]
0x18008ee96  lea     rdx, byte_1800DDC84
0x18008ee9d  xor     r9d, r9d
0x18008eea0  mov     r8d, edi
0x18008eea3  mov     rax, [rcx]
0x18008eea6  mov     rax, [rax+20h]
0x18008eeaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008eeaf  jmp     short loc_18008EEBB
0x18008eeb1  mov     rcx, [rbp+var_18]
0x18008eeb5  call    cs:__imp_HrRewindStream
0x18008eebb  mov     ebx, eax
0x18008eebd  test    eax, eax
0x18008eebf  js      short loc_18008EF01
0x18008eec1  mov     r8d, 36h ; '6'
0x18008eec7  lea     rdx, aSavedFromUrl00_0; "<!-- saved from url=(0022)http://intern"...
0x18008eece  mov     rcx, [rbp+var_10]
0x18008eed2  xor     r9d, r9d
0x18008eed5  mov     rax, [rcx]
0x18008eed8  mov     rax, [rax+20h]
0x18008eedc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008eee1  mov     ebx, eax
0x18008eee3  test    eax, eax
0x18008eee5  js      short loc_18008EF01
0x18008eee7  mov     rdx, [rbp+var_10]
0x18008eeeb  xor     r8d, r8d
0x18008eeee  mov     rcx, [rbp+var_18]
0x18008eef2  call    cs:__imp_HrCopyStream
0x18008eef8  mov     ebx, eax
0x18008eefa  jmp     short loc_18008EF01
0x18008eefc  mov     ebx, 80070057h
0x18008ef01  lea     rcx, [rbp+var_18]
0x18008ef05  call    ??$OE_SafeReleaseAndNullPtr@UIStream@@@@YAXAEAPEAUIStream@@@Z; OE_SafeReleaseAndNullPtr<IStream>(IStream * &)
0x18008ef0a  lea     rcx, [rbp+var_10]
0x18008ef0e  call    ??$OE_SafeReleaseAndNullPtr@UIStream@@@@YAXAEAPEAUIStream@@@Z; OE_SafeReleaseAndNullPtr<IStream>(IStream * &)
0x18008ef13  mov     rdi, [rsp+50h+arg_10]
0x18008ef18  mov     eax, ebx
0x18008ef1a  mov     rbx, [rsp+50h+arg_8]
0x18008ef1f  add     rsp, 50h
0x18008ef23  pop     rbp
0x18008ef24  retn
```
