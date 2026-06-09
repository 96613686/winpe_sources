# CTxtEdit::OnDropFiles(void *)

- ea: `0x18005decc`
- end: `0x18005e1fc`
- name: `?OnDropFiles@CTxtEdit@@AEAA_JPEAX@Z`
- size: `816`
- prototype: `__int64 __fastcall(CTxtEdit *__hidden this, void *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180027b20`

## callees

- `0x180009070`
- `0x180017cdc`
- `0x18002c58c`
- `0x18002c650`
- `0x180035b80`
- `0x18003c554`
- `0x18003e088`
- `0x18003ebc4`
- `0x18003f328`
- `0x1800468bc`
- `0x18005d8d0`
- `0x18005decc`
- `0x1800921e8`
- `0x180093c00`
- `0x180095010`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x18005e180`
- `KERNEL32!MultiByteToWideChar` at `0x18005e180`
- `KERNEL32!GetProcAddress` at `0x18005df4b`
- `KERNEL32!GetProcAddress` at `0x18005df69`
- `KERNEL32!GetProcAddress` at `0x18005df87`
- `KERNEL32!GetProcAddress` at `0x18005dfa5`
- `KERNEL32!GetProcAddress` at `0x18005df4b`
- `KERNEL32!GetProcAddress` at `0x18005df69`
- `KERNEL32!GetProcAddress` at `0x18005df87`
- `KERNEL32!GetProcAddress` at `0x18005dfa5`
- `KERNEL32!FreeLibrary` at `0x18005e1c3`
- `KERNEL32!FreeLibrary` at `0x18005e1c3`

## string_xrefs

- `0x18005df29`: `Shell32.DLL`

## pseudocode

```c
__int64 __fastcall CTxtEdit::OnDropFiles(CTxtEdit *this, void *a2)
{
  __int64 v4; // rdx
  unsigned int v5; // r8d
  struct CTxtSelection *Sel; // r13
  HINSTANCE Library; // rax
  HMODULE v8; // r15
  FARPROC v9; // rbx
  FARPROC v10; // rsi
  FARPROC v11; // rax
  __int64 (__fastcall *v12)(_QWORD, _QWORD, _QWORD, _QWORD); // rax
  unsigned int v13; // r12d
  __int64 v14; // rbx
  int CpFromAcp; // esi
  const struct CCharFormat *CF; // rbx
  int v17; // r8d
  int iCF; // eax
  int v19; // ebx
  bool v20; // zf
  int v21; // r8d
  unsigned int v22; // ebx
  void (__fastcall *v23)(_QWORD, _QWORD, _QWORD, _QWORD); // r13
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  const struct CCharFormat *CharFormat; // [rsp+58h] [rbp-A8h]
  INT_PTR (__stdcall *v27)(); // [rsp+60h] [rbp-A0h]
  FARPROC v28; // [rsp+68h] [rbp-98h]
  FARPROC ProcAddress; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+78h] [rbp-88h] BYREF
  __int128 v31; // [rsp+80h] [rbp-80h]
  void *v32; // [rsp+90h] [rbp-70h]
  int v33[2]; // [rsp+98h] [rbp-68h]
  _BYTE v34[32]; // [rsp+A0h] [rbp-60h] BYREF
  int v35; // [rsp+C0h] [rbp-40h]
  CHAR MultiByteStr[272]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR WideCharStr[264]; // [rsp+200h] [rbp+100h] BYREF

  v25 = 0;
  Sel = CTxtEdit::GetSel(this);
  if ( Sel )
  {
    if ( (*((_BYTE *)this + 180) & 4) == 0 )
    {
      Library = CW32System::LoadLibrary(L"Shell32.DLL", v4, v5);
      v8 = Library;
      if ( Library )
      {
        ProcAddress = GetProcAddress(Library, "DragFinish");
        v9 = GetProcAddress(v8, "DragQueryFileA");
        v28 = v9;
        v10 = GetProcAddress(v8, "DragQueryFileW");
        v27 = v10;
        v11 = GetProcAddress(v8, "DragQueryPoint");
        if ( !ProcAddress || !v9 || !v10 || !v11 )
          goto LABEL_30;
        ((void (__fastcall *)(void *, __int64 *))v11)(a2, &v25);
        v12 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))v9;
        if ( CW32System::_dwPlatformId != 1 )
          v12 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))v10;
        v13 = v12(a2, 0xFFFFFFFFLL, 0, 0);
        if ( v13 )
        {
          v14 = v25;
          CRchTxtPtr::CRchTxtPtr((CRchTxtPtr *)v34, this);
          if ( (*(int (__fastcall **)(_QWORD, __int64, _QWORD, _BYTE *, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 8) + 232LL))(
                 *((_QWORD *)this + 8),
                 v14,
                 0,
                 v34,
                 0,
                 0,
                 0,
                 0,
                 0) < 0 )
          {
            iCF = CTxtRange::Get_iCF(Sel);
            CpFromAcp = *((_DWORD *)Sel + 10);
            v19 = iCF;
            CharFormat = CTxtArray::GetCharFormat((CTxtEdit *)((char *)this + 248), iCF);
            ReleaseFormats(v19, -1);
            CF = CharFormat;
          }
          else
          {
            CpFromAcp = v35;
            CF = CRchTxtPtr::GetCF((CRchTxtPtr *)v34);
          }
          if ( (*((_DWORD *)this + 44) & 0x100000) != 0 )
          {
            v20 = (*((_DWORD *)this + 45) & 0x80000) == 0;
            v31 = 0;
            v30 = 0;
            *(_QWORD *)v33 = 0;
            v32 = a2;
            if ( v20 )
              v33[0] = CpFromAcp;
            else
              v33[0] = CTxtEdit::GetAcpFromCp(this, CpFromAcp, v17);
            v33[1] = (*(unsigned __int8 *)CF >> 4) & 1;
            if ( (unsigned int)CTxtEdit::TxNotify(this, 0x703u, &v30) )
            {
LABEL_29:
              ((void (__fastcall *)(void *))ProcAddress)(a2);
LABEL_30:
              FreeLibrary(v8);
              return 0;
            }
            if ( (*((_DWORD *)this + 45) & 0x80000) != 0 )
              CpFromAcp = CTxtEdit::GetCpFromAcp(this, v33[0], v21);
            else
              CpFromAcp = v33[0];
          }
          CTxtRange::SetCp(Sel, CpFromAcp);
          v10 = v27;
        }
        v22 = 0;
        if ( v13 )
        {
          v23 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))v28;
          do
          {
            if ( CW32System::_dwPlatformId == 1 )
            {
              v23(a2, v22, MultiByteStr, 260);
              MultiByteToWideChar(0, 0, MultiByteStr, -1, WideCharStr, 260);
            }
            else
            {
              ((void (__fastcall *)(void *, _QWORD, WCHAR *, __int64))v10)(a2, v22, WideCharStr, 260);
            }
            CTxtEdit::InsertFromFile(this, WideCharStr);
            ++v22;
          }
          while ( v22 < v13 );
        }
        goto LABEL_29;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18005decc  mov     [rsp-8+arg_10], rbx
0x18005ded1  push    rbp
0x18005ded2  push    rsi
0x18005ded3  push    rdi
0x18005ded4  push    r12
0x18005ded6  push    r13
0x18005ded8  push    r14
0x18005deda  push    r15
0x18005dedc  lea     rbp, [rsp-320h]
0x18005dee4  sub     rsp, 420h
0x18005deeb  mov     rax, cs:__security_cookie
0x18005def2  xor     rax, rsp
0x18005def5  mov     [rbp+350h+var_40], rax
0x18005defc  mov     r14, rdx
0x18005deff  mov     [rsp+450h+var_400], 0
0x18005df08  mov     rdi, rcx
0x18005df0b  call    ?GetSel@CTxtEdit@@QEAAPEAVCTxtSelection@@XZ; CTxtEdit::GetSel(void)
0x18005df10  mov     r13, rax
0x18005df13  test    rax, rax
0x18005df16  jz      loc_18005E1CF
0x18005df1c  test    byte ptr [rdi+0B4h], 4
0x18005df23  jnz     loc_18005E1CF
0x18005df29  lea     rcx, aShell32Dll; "Shell32.DLL"
0x18005df30  call    ?LoadLibrary@CW32System@@SAPEAUHINSTANCE__@@PEBG@Z; CW32System::LoadLibrary(ushort const *)
0x18005df35  mov     r15, rax
0x18005df38  test    rax, rax
0x18005df3b  jz      loc_18005E1CF
0x18005df41  lea     rdx, aDragfinish; "DragFinish"
0x18005df48  mov     rcx, rax; hModule
0x18005df4b  call    cs:__imp_GetProcAddress
0x18005df52  nop     dword ptr [rax+rax+00h]
0x18005df57  lea     rdx, aDragqueryfilea; "DragQueryFileA"
0x18005df5e  mov     rcx, r15; hModule
0x18005df61  mov     r12, rax
0x18005df64  mov     [rsp+450h+var_3E0], rax
0x18005df69  call    cs:__imp_GetProcAddress
0x18005df70  nop     dword ptr [rax+rax+00h]
0x18005df75  lea     rdx, aDragqueryfilew; "DragQueryFileW"
0x18005df7c  mov     rcx, r15; hModule
0x18005df7f  mov     rbx, rax
0x18005df82  mov     [rsp+450h+var_3E8], rax
0x18005df87  call    cs:__imp_GetProcAddress
0x18005df8e  nop     dword ptr [rax+rax+00h]
0x18005df93  lea     rdx, aDragquerypoint; "DragQueryPoint"
0x18005df9a  mov     rcx, r15; hModule
0x18005df9d  mov     rsi, rax
0x18005dfa0  mov     [rsp+450h+var_3F0], rax
0x18005dfa5  call    cs:__imp_GetProcAddress
0x18005dfac  nop     dword ptr [rax+rax+00h]
0x18005dfb1  test    r12, r12
0x18005dfb4  jz      loc_18005E1C0
0x18005dfba  test    rbx, rbx
0x18005dfbd  jz      loc_18005E1C0
0x18005dfc3  test    rsi, rsi
0x18005dfc6  jz      loc_18005E1C0
0x18005dfcc  test    rax, rax
0x18005dfcf  jz      loc_18005E1C0
0x18005dfd5  lea     rdx, [rsp+450h+var_400]
0x18005dfda  mov     rcx, r14
0x18005dfdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dfe2  xor     r9d, r9d
0x18005dfe5  xor     r8d, r8d
0x18005dfe8  or      edx, 0FFFFFFFFh
0x18005dfeb  mov     rcx, r14
0x18005dfee  cmp     cs:?_dwPlatformId@CW32System@@0KA, 1; ulong CW32System::_dwPlatformId
0x18005dff5  mov     rax, rbx
0x18005dff8  jz      short loc_18005DFFD
0x18005dffa  mov     rax, rsi
0x18005dffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e002  mov     r12d, eax
0x18005e005  test    eax, eax
0x18005e007  jz      loc_18005E134
0x18005e00d  mov     rbx, [rsp+450h+var_400]
0x18005e012  lea     rcx, [rbp+350h+var_3B0]; this
0x18005e016  mov     rdx, rdi; struct CTxtEdit *
0x18005e019  call    ??0CRchTxtPtr@@QEAA@PEAVCTxtEdit@@@Z; CRchTxtPtr::CRchTxtPtr(CTxtEdit *)
0x18005e01e  mov     rcx, [rdi+40h]
0x18005e022  lea     r9, [rbp+350h+var_3B0]
0x18005e026  xor     esi, esi
0x18005e028  xor     r8d, r8d
0x18005e02b  mov     [rsp+450h+var_410], rsi
0x18005e030  mov     rdx, rbx
0x18005e033  mov     [rsp+450h+var_418], rsi
0x18005e038  mov     rax, [rcx]
0x18005e03b  mov     [rsp+450h+var_420], rsi
0x18005e040  mov     [rsp+450h+cchWideChar], esi
0x18005e044  mov     [rsp+450h+lpWideCharStr], rsi
0x18005e049  mov     rax, [rax+0E8h]
0x18005e050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e055  test    eax, eax
0x18005e057  js      short loc_18005E06A
0x18005e059  mov     esi, [rbp+350h+var_390]
0x18005e05c  lea     rcx, [rbp+350h+var_3B0]; this
0x18005e060  call    ?GetCF@CRchTxtPtr@@QEBAPEBVCCharFormat@@XZ; CRchTxtPtr::GetCF(void)
0x18005e065  mov     rbx, rax
0x18005e068  jmp     short loc_18005E09A
0x18005e06a  mov     rcx, r13; this
0x18005e06d  call    ?Get_iCF@CTxtRange@@QEAAJXZ; CTxtRange::Get_iCF(void)
0x18005e072  mov     esi, [r13+28h]
0x18005e076  lea     rcx, [rdi+0F8h]; this
0x18005e07d  mov     edx, eax; int
0x18005e07f  mov     ebx, eax
0x18005e081  call    ?GetCharFormat@CTxtArray@@QEAAPEBVCCharFormat@@J@Z; CTxtArray::GetCharFormat(long)
0x18005e086  or      edx, 0FFFFFFFFh; int
0x18005e089  mov     [rsp+450h+var_3F8], rax
0x18005e08e  mov     ecx, ebx; int
0x18005e090  call    ?ReleaseFormats@@YAXJJ@Z; ReleaseFormats(long,long)
0x18005e095  mov     rbx, [rsp+450h+var_3F8]
0x18005e09a  test    dword ptr [rdi+0B0h], 100000h
0x18005e0a4  jz      short loc_18005E125
0x18005e0a6  test    dword ptr [rdi+0B4h], 80000h
0x18005e0b0  xorps   xmm0, xmm0
0x18005e0b3  movdqu  [rbp+350h+var_3D0], xmm0
0x18005e0b8  mov     [rsp+450h+var_3D8], 0
0x18005e0c1  mov     qword ptr [rbp+350h+var_3B8], 0
0x18005e0c9  mov     [rbp+350h+var_3C0], r14
0x18005e0cd  jz      short loc_18005E0DE
0x18005e0cf  mov     edx, esi; int
0x18005e0d1  mov     rcx, rdi; this
0x18005e0d4  call    ?GetAcpFromCp@CTxtEdit@@QEAAJJH@Z; CTxtEdit::GetAcpFromCp(long,int)
0x18005e0d9  mov     [rbp+350h+var_3B8], eax
0x18005e0dc  jmp     short loc_18005E0E1
0x18005e0de  mov     [rbp+350h+var_3B8], esi
0x18005e0e1  movzx   eax, byte ptr [rbx]
0x18005e0e4  lea     r8, [rsp+450h+var_3D8]; void *
0x18005e0e9  shr     eax, 4
0x18005e0ec  mov     edx, 703h; unsigned int
0x18005e0f1  and     eax, 1
0x18005e0f4  mov     rcx, rdi; this
0x18005e0f7  mov     [rbp+350h+var_3B8+4], eax
0x18005e0fa  call    ?TxNotify@CTxtEdit@@QEAAJKPEAX@Z; CTxtEdit::TxNotify(ulong,void *)
0x18005e0ff  test    eax, eax
0x18005e101  jnz     loc_18005E1B3
0x18005e107  test    dword ptr [rdi+0B4h], 80000h
0x18005e111  jz      short loc_18005E122
0x18005e113  mov     edx, [rbp+350h+var_3B8]; int
0x18005e116  mov     rcx, rdi; this
0x18005e119  call    ?GetCpFromAcp@CTxtEdit@@QEAAJJH@Z; CTxtEdit::GetCpFromAcp(long,int)
0x18005e11e  mov     esi, eax
0x18005e120  jmp     short loc_18005E125
0x18005e122  mov     esi, [rbp+350h+var_3B8]
0x18005e125  mov     edx, esi; int
0x18005e127  mov     rcx, r13; this
0x18005e12a  call    ?SetCp@CTxtRange@@QEAAJJ@Z; CTxtRange::SetCp(long)
0x18005e12f  mov     rsi, [rsp+450h+var_3F0]
0x18005e134  xor     ebx, ebx
0x18005e136  test    r12d, r12d
0x18005e139  jz      short loc_18005E1B3
0x18005e13b  mov     r13, [rsp+450h+var_3E8]
0x18005e140  cmp     cs:?_dwPlatformId@CW32System@@0KA, 1; ulong CW32System::_dwPlatformId
0x18005e147  mov     r9d, 104h
0x18005e14d  mov     edx, ebx
0x18005e14f  mov     rcx, r14
0x18005e152  jnz     short loc_18005E18E
0x18005e154  lea     r8, [rbp+350h+MultiByteStr]
0x18005e158  mov     rax, r13
0x18005e15b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e160  lea     rax, [rbp+350h+WideCharStr]
0x18005e167  mov     [rsp+450h+cchWideChar], 104h; cchWideChar
0x18005e16f  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18005e173  mov     [rsp+450h+lpWideCharStr], rax; lpWideCharStr
0x18005e178  lea     r8, [rbp+350h+MultiByteStr]; lpMultiByteStr
0x18005e17c  xor     edx, edx; dwFlags
0x18005e17e  xor     ecx, ecx; CodePage
0x18005e180  call    cs:__imp_MultiByteToWideChar
0x18005e187  nop     dword ptr [rax+rax+00h]
0x18005e18c  jmp     short loc_18005E19D
0x18005e18e  lea     r8, [rbp+350h+WideCharStr]
0x18005e195  mov     rax, rsi
0x18005e198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e19d  lea     rdx, [rbp+350h+WideCharStr]; unsigned __int16 *
0x18005e1a4  mov     rcx, rdi; this
0x18005e1a7  call    ?InsertFromFile@CTxtEdit@@AEAA_JPEBG@Z; CTxtEdit::InsertFromFile(ushort const *)
0x18005e1ac  inc     ebx
0x18005e1ae  cmp     ebx, r12d
0x18005e1b1  jb      short loc_18005E140
0x18005e1b3  mov     rax, [rsp+450h+var_3E0]
0x18005e1b8  mov     rcx, r14
0x18005e1bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e1c0  mov     rcx, r15; hLibModule
0x18005e1c3  call    cs:__imp_FreeLibrary
0x18005e1ca  nop     dword ptr [rax+rax+00h]
0x18005e1cf  xor     eax, eax
0x18005e1d1  mov     rcx, [rbp+350h+var_40]
0x18005e1d8  xor     rcx, rsp; StackCookie
0x18005e1db  call    __security_check_cookie
0x18005e1e0  mov     rbx, [rsp+450h+arg_10]
0x18005e1e8  add     rsp, 420h
0x18005e1ef  pop     r15
0x18005e1f1  pop     r14
0x18005e1f3  pop     r13
0x18005e1f5  pop     r12
0x18005e1f7  pop     rdi
0x18005e1f8  pop     rsi
0x18005e1f9  pop     rbp
0x18005e1fa  retn
```
