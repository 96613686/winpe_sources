# CModule::WriteEffectApplicableFlag(DXGI_EFFECT_TYPE)

- ea: `0x18006e404`
- end: `0x18006e5b1`
- name: `?WriteEffectApplicableFlag@CModule@@QEAAXW4DXGI_EFFECT_TYPE@@@Z`
- size: `429`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180027944`

## callees

- `0x18000c6b0`
- `0x18006e404`
- `0x180075fa0`
- `0x180076f20`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18006e446`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18006e446`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e450`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e450`
- `ext-ms-win-dx-dxdbhelper-l1-1-1!__imp_WriteUserSetting` at `0x18006e4d3`
- `ext-ms-win-dx-dxdbhelper-l1-1-1!__imp_WriteUserSetting` at `0x18006e569`
- `ext-ms-win-dx-dxdbhelper-l1-1-1!__imp_WriteUserSetting` at `0x18006e4d3`
- `ext-ms-win-dx-dxdbhelper-l1-1-1!__imp_WriteUserSetting` at `0x18006e569`

## string_xrefs

- `0x18006e4ec`: `Failed to write AUTOHDR_ENABLE user setting (non-fatal)`
- `0x18006e582`: `Failed to write applicable flag`

## pseudocode

```c
void __fastcall CModule::WriteEffectApplicableFlag(__int64 a1, int a2)
{
  int v3; // ebx
  signed int LastError; // eax
  CModule *v5; // rcx
  bool v6; // r9
  int v7; // edi
  unsigned int v8; // eax
  bool v9; // r9
  CModule *v10; // rcx
  unsigned int v11; // eax
  bool v12; // r9
  CModule *v13; // rcx
  _DWORD v14[4]; // [rsp+40h] [rbp-238h] BYREF
  WCHAR Filename[264]; // [rsp+50h] [rbp-228h] BYREF

  v3 = 0;
  memset_0(Filename, 0, 0x208u);
  if ( !GetModuleFileNameW(0, Filename, 0x104u) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 < 0 )
      CModule::RecordJournalImpl(v5, v3, "GetModuleFileName failed", v6);
  }
  if ( a2 == 1 )
  {
    if ( (dword_180109BC4 & 0x800) == 0 )
    {
      v7 = dword_180109BC4 | 0x800;
      if ( v3 >= 0 )
      {
        v14[0] = dword_180109BC4 & 0xFFFF10F0 | 0x801;
        v8 = WriteUserSetting(9, 0, v14, 4, Filename, 0, 0);
        v10 = (CModule *)(v8 + 0x80000000);
        if ( (int)v10 >= 0 && v8 != -2147024891 )
          CModule::RecordJournalImpl(v10, v8, "Failed to write AUTOHDR_ENABLE user setting (non-fatal)", v9);
      }
      dword_180109BC4 = v7;
    }
  }
  else if ( ((unsigned __int8)(1 << a2) & BYTE4(qword_180109C48)) == 0 )
  {
    BYTE4(qword_180109C48) |= 1 << a2;
    v14[1] = HIDWORD(qword_180109C48) & 0xFFFFA0FF;
    v14[0] = (unsigned __int16)qword_180109C48;
    v11 = WriteUserSetting(13, 0, v14, 8, Filename, 0, 0);
    v13 = (CModule *)(v11 + 0x80000000);
    if ( (int)v13 >= 0 && v11 != -2147024891 )
      CModule::RecordJournalImpl(v13, v11, "Failed to write applicable flag", v12);
  }
}

```

## disassembly

```asm
0x18006e404  mov     [rsp+arg_0], rbx
0x18006e409  push    rdi
0x18006e40a  sub     rsp, 270h
0x18006e411  mov     rax, cs:__security_cookie
0x18006e418  xor     rax, rsp
0x18006e41b  mov     [rsp+278h+var_18], rax
0x18006e423  mov     edi, edx
0x18006e425  lea     rcx, [rsp+278h+Filename]; void *
0x18006e42a  xor     edx, edx; Val
0x18006e42c  mov     r8d, 208h; Size
0x18006e432  xor     ebx, ebx
0x18006e434  call    memset_0
0x18006e439  mov     r8d, 104h; nSize
0x18006e43f  lea     rdx, [rsp+278h+Filename]; lpFilename
0x18006e444  xor     ecx, ecx; hModule
0x18006e446  call    cs:__imp_GetModuleFileNameW
0x18006e44c  test    eax, eax
0x18006e44e  jnz     short loc_18006E477
0x18006e450  call    cs:__imp_GetLastError
0x18006e456  mov     ebx, eax
0x18006e458  test    eax, eax
0x18006e45a  jle     short loc_18006E465
0x18006e45c  movzx   ebx, ax
0x18006e45f  or      ebx, 80070000h
0x18006e465  test    ebx, ebx
0x18006e467  jns     short loc_18006E477
0x18006e469  lea     r8, aGetmodulefilen; "GetModuleFileName failed"
0x18006e470  mov     edx, ebx; unsigned int
0x18006e472  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x18006e477  mov     edx, 1
0x18006e47c  cmp     edi, edx
0x18006e47e  jnz     loc_18006E505
0x18006e484  mov     edi, cs:dword_180109BC4
0x18006e48a  mov     eax, 800h
0x18006e48f  test    eax, edi
0x18006e491  jnz     loc_18006E590
0x18006e497  or      edi, eax
0x18006e499  test    ebx, ebx
0x18006e49b  js      short loc_18006E4FA
0x18006e49d  mov     eax, edi
0x18006e49f  mov     [rsp+278h+var_248], 0
0x18006e4a8  and     eax, 0FFFF18F1h
0x18006e4ad  mov     [rsp+278h+var_250], 0
0x18006e4b5  or      eax, edx
0x18006e4b7  lea     r9d, [rdx+3]
0x18006e4bb  xor     edx, edx
0x18006e4bd  mov     [rsp+278h+var_238], eax
0x18006e4c1  lea     rax, [rsp+278h+Filename]
0x18006e4c6  lea     r8, [rsp+278h+var_238]
0x18006e4cb  mov     [rsp+278h+var_258], rax
0x18006e4d0  lea     ecx, [rdx+9]
0x18006e4d3  call    cs:__imp_WriteUserSetting
0x18006e4d9  mov     edx, 80000000h
0x18006e4de  lea     ecx, [rax+rdx]; this
0x18006e4e1  test    edx, ecx
0x18006e4e3  jnz     short loc_18006E4FA
0x18006e4e5  cmp     eax, 80070005h
0x18006e4ea  jz      short loc_18006E4FA
0x18006e4ec  lea     r8, aFailedToWriteA_0; "Failed to write AUTOHDR_ENABLE user set"...
0x18006e4f3  mov     edx, eax; unsigned int
0x18006e4f5  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x18006e4fa  mov     cs:dword_180109BC4, edi
0x18006e500  jmp     loc_18006E590
0x18006e505  mov     al, byte ptr cs:qword_180109C48+4
0x18006e50b  mov     cl, dil
0x18006e50e  shl     edx, cl
0x18006e510  test    al, dl
0x18006e512  jnz     short loc_18006E590
0x18006e514  or      al, dl
0x18006e516  mov     [rsp+278h+var_248], 0
0x18006e51f  mov     byte ptr cs:qword_180109C48+4, al
0x18006e525  lea     r8, [rsp+278h+var_238]
0x18006e52a  mov     rax, cs:qword_180109C48
0x18006e531  xor     edx, edx
0x18006e533  mov     qword ptr [rsp+278h+var_238], rax
0x18006e538  mov     r9d, 8
0x18006e53e  shr     rax, 20h
0x18006e542  and     eax, 0FFFFA0FFh
0x18006e547  mov     [rsp+278h+var_250], 0
0x18006e54f  mov     [rsp+278h+var_238+4], eax
0x18006e553  lea     ecx, [rdx+0Dh]
0x18006e556  movzx   eax, word ptr [rsp+278h+var_238]
0x18006e55b  mov     [rsp+278h+var_238], eax
0x18006e55f  lea     rax, [rsp+278h+Filename]
0x18006e564  mov     [rsp+278h+var_258], rax
0x18006e569  call    cs:__imp_WriteUserSetting
0x18006e56f  mov     edx, 80000000h
0x18006e574  lea     ecx, [rax+rdx]; this
0x18006e577  test    edx, ecx
0x18006e579  jnz     short loc_18006E590
0x18006e57b  cmp     eax, 80070005h
0x18006e580  jz      short loc_18006E590
0x18006e582  lea     r8, aFailedToWriteA; "Failed to write applicable flag"
0x18006e589  mov     edx, eax; unsigned int
0x18006e58b  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x18006e590  mov     rcx, [rsp+278h+var_18]
0x18006e598  xor     rcx, rsp; StackCookie
0x18006e59b  call    __security_check_cookie
0x18006e5a0  mov     rbx, [rsp+278h+arg_0]
0x18006e5a8  add     rsp, 270h
0x18006e5af  pop     rdi
0x18006e5b0  retn
```
