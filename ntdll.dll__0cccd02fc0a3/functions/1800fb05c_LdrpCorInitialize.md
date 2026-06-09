# LdrpCorInitialize

- ea: `0x1800fb05c`
- end: `0x1800fb267`
- name: `LdrpCorInitialize`
- size: `523`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800d6508`

## callees

- `0x18001d490`
- `0x18001e820`
- `0x180023e20`
- `0x180024eb0`
- `0x18002c6f0`
- `0x1800535c0`
- `0x180053ab0`
- `0x180054000`
- `0x18008e8e0`
- `0x1800fb05c`
- `0x1800fb270`
- `0x180162000`
- `0x18016f030`

## string_xrefs

- `0x1800fb0ee`: `COMPLUS_InstallRoot`
- `0x1800fb11f`: `COMPLUS_Version`

## pseudocode

```c
__int64 __fastcall LdrpCorInitialize(_QWORD *a1)
{
  bool v2; // bl
  int Dll; // ebx
  unsigned __int16 *v4; // rdi
  __int64 v6; // rdi
  __int64 v7; // [rsp+38h] [rbp-1C0h] BYREF
  unsigned __int64 v8; // [rsp+40h] [rbp-1B8h] BYREF
  char ArgList[4]; // [rsp+50h] [rbp-1A8h] BYREF
  _WORD *v10; // [rsp+58h] [rbp-1A0h]
  _WORD v11[128]; // [rsp+60h] [rbp-198h] BYREF
  _BYTE v12[128]; // [rsp+160h] [rbp-98h] BYREF

  v8 = 0;
  memset_thunk_772440563353939046(v12, 0, 0x80u);
  v2 = 1;
  v7 = 0;
  memset_thunk_772440563353939046(ArgList, 0, 0x110u);
  RtlEnterCriticalSection(&FastPebLock);
  if ( (unsigned int)RtlQueryEnvironmentVariable(0, L"COMPLUS_InstallRoot", 19) == -1073741789 )
    v2 = (unsigned int)RtlQueryEnvironmentVariable(0, L"COMPLUS_Version", 15) != -1073741789;
  RtlLeaveCriticalSection(&FastPebLock);
  v10 = v11;
  *(_DWORD *)ArgList = 0x1000000;
  v11[0] = 0;
  if ( v2 )
  {
    Dll = LdrpBuildSystem32FileName(ArgList, &LdrpMscoreeDllName);
    v4 = (unsigned __int16 *)ArgList;
  }
  else
  {
    v4 = (unsigned __int16 *)&LdrpMscoreeDllName;
    Dll = 0;
  }
  if ( Dll >= 0 )
  {
    memset_thunk_772440563353939046(v12, 0, 0x80u);
    Dll = LdrpLoadDll(v4, (__int64)v12, 1u, (__int64)&v7);
    LdrpReleaseDllPath(v12);
    if ( Dll >= 0 )
    {
      v6 = v7;
      Dll = LdrpGetProcedureAddress(*(_QWORD *)(v7 + 48), "_CorExeMain", 0, &v8);
      if ( Dll < 0 )
      {
        LdrpDecrementModuleLoadCountEx(v6, 0);
      }
      else
      {
        LdrpCorExeMainRoutine = __ROR8__(v8 ^ MEMORY[0x7FFE0330], MEMORY[0x7FFE0330] & 0x3F);
        *a1 = v6;
      }
      LdrpDereferenceModule(v6);
    }
  }
  if ( v11 != v10 )
    RtlpSysVolFree(v10);
  return (unsigned int)Dll;
}

```

## disassembly

```asm
0x1800fb05c  mov     [rsp+arg_8], rbx
0x1800fb061  mov     [rsp+arg_10], rsi
0x1800fb066  push    rdi
0x1800fb067  sub     rsp, 1F0h
0x1800fb06e  mov     rax, cs:__security_cookie
0x1800fb075  xor     rax, rsp
0x1800fb078  mov     [rsp+1F8h+var_18], rax
0x1800fb080  mov     rsi, rcx
0x1800fb083  mov     [rsp+1F8h+var_1B8], 0
0x1800fb08c  xor     edx, edx; Val
0x1800fb08e  mov     r8d, 80h; Size
0x1800fb094  lea     rcx, [rsp+1F8h+var_98]; void *
0x1800fb09c  call    memset$thunk$772440563353939046
0x1800fb0a1  mov     bl, 1
0x1800fb0a3  mov     [rsp+1F8h+var_1C0], 0
0x1800fb0ac  xor     edx, edx; Val
0x1800fb0ae  mov     r8d, 110h; Size
0x1800fb0b4  lea     rcx, [rsp+1F8h+ArgList]; void *
0x1800fb0b9  call    memset$thunk$772440563353939046
0x1800fb0be  mov     [rsp+1F8h+var_1C8], 0
0x1800fb0c7  lea     rcx, FastPebLock
0x1800fb0ce  call    RtlEnterCriticalSection
0x1800fb0d3  nop
0x1800fb0d4  lea     rax, [rsp+1F8h+var_1C8]
0x1800fb0d9  mov     [rsp+1F8h+var_1D0], rax
0x1800fb0de  mov     [rsp+1F8h+var_1D8], 0
0x1800fb0e7  xor     r9d, r9d
0x1800fb0ea  lea     r8d, [r9+13h]
0x1800fb0ee  lea     rdx, LdrpComPlusInstallRootName; "COMPLUS_InstallRoot"
0x1800fb0f5  xor     ecx, ecx
0x1800fb0f7  call    RtlQueryEnvironmentVariable
0x1800fb0fc  mov     edi, 0C0000023h
0x1800fb101  cmp     eax, edi
0x1800fb103  jnz     short loc_1800FB137
0x1800fb105  lea     rax, [rsp+1F8h+var_1C8]
0x1800fb10a  mov     [rsp+1F8h+var_1D0], rax
0x1800fb10f  mov     [rsp+1F8h+var_1D8], 0
0x1800fb118  xor     r9d, r9d
0x1800fb11b  lea     r8d, [r9+0Fh]
0x1800fb11f  lea     rdx, LdrpComPlusVersionName; "COMPLUS_Version"
0x1800fb126  xor     ecx, ecx
0x1800fb128  call    RtlQueryEnvironmentVariable
0x1800fb12d  movzx   ebx, bl
0x1800fb130  xor     edx, edx
0x1800fb132  cmp     eax, edi
0x1800fb134  cmovz   ebx, edx
0x1800fb137  lea     rcx, FastPebLock
0x1800fb13e  call    RtlLeaveCriticalSection
0x1800fb143  lea     rax, [rsp+1F8h+var_198]
0x1800fb148  mov     [rsp+1F8h+var_1A0], rax
0x1800fb14d  mov     dword ptr [rsp+1F8h+ArgList], 1000000h
0x1800fb155  xor     eax, eax
0x1800fb157  mov     [rsp+1F8h+var_198], ax
0x1800fb15c  test    bl, bl
0x1800fb15e  jz      loc_1800FB259
0x1800fb164  lea     rdx, LdrpMscoreeDllName
0x1800fb16b  lea     rcx, [rsp+1F8h+ArgList]
0x1800fb170  call    LdrpBuildSystem32FileName
0x1800fb175  mov     ebx, eax
0x1800fb177  lea     rdi, [rsp+1F8h+ArgList]
0x1800fb17c  test    ebx, ebx
0x1800fb17e  jns     short loc_1800FB1BC
0x1800fb180  lea     rax, [rsp+1F8h+var_198]
0x1800fb185  mov     rcx, [rsp+1F8h+var_1A0]
0x1800fb18a  cmp     rax, rcx
0x1800fb18d  jz      short loc_1800FB194
0x1800fb18f  call    RtlpSysVolFree
0x1800fb194  mov     eax, ebx
0x1800fb196  mov     rcx, [rsp+1F8h+var_18]
0x1800fb19e  xor     rcx, rsp; StackCookie
0x1800fb1a1  call    __security_check_cookie
0x1800fb1a6  lea     r11, [rsp+1F8h+var_8]
0x1800fb1ae  mov     rbx, [r11+18h]
0x1800fb1b2  mov     rsi, [r11+20h]
0x1800fb1b6  mov     rsp, r11
0x1800fb1b9  pop     rdi
0x1800fb1ba  retn
0x1800fb1bc  xor     edx, edx; Val
0x1800fb1be  mov     r8d, 80h; Size
0x1800fb1c4  lea     rcx, [rsp+1F8h+var_98]; void *
0x1800fb1cc  call    memset$thunk$772440563353939046
0x1800fb1d1  lea     r9, [rsp+1F8h+var_1C0]
0x1800fb1d6  mov     r8d, 1
0x1800fb1dc  lea     rdx, [rsp+1F8h+var_98]
0x1800fb1e4  mov     rcx, rdi; ArgList
0x1800fb1e7  call    LdrpLoadDll
0x1800fb1ec  mov     ebx, eax
0x1800fb1ee  lea     rcx, [rsp+1F8h+var_98]
0x1800fb1f6  call    LdrpReleaseDllPath
0x1800fb1fb  test    ebx, ebx
0x1800fb1fd  js      short loc_1800FB180
0x1800fb1ff  lea     r9, [rsp+1F8h+var_1B8]
0x1800fb204  xor     r8d, r8d
0x1800fb207  lea     rdx, aCorexemain; "_CorExeMain"
0x1800fb20e  mov     rdi, [rsp+1F8h+var_1C0]
0x1800fb213  mov     rcx, [rdi+30h]
0x1800fb217  call    LdrpGetProcedureAddress
0x1800fb21c  mov     ebx, eax
0x1800fb21e  test    eax, eax
0x1800fb220  js      short loc_1800FB24D
0x1800fb222  mov     eax, ds:7FFE0330h
0x1800fb229  mov     ecx, eax
0x1800fb22b  and     ecx, 3Fh
0x1800fb22e  xor     rax, [rsp+1F8h+var_1B8]
0x1800fb233  ror     rax, cl
0x1800fb236  mov     cs:LdrpCorExeMainRoutine, rax
0x1800fb23d  mov     [rsi], rdi
0x1800fb240  mov     rcx, rdi
0x1800fb243  call    LdrpDereferenceModule
0x1800fb248  jmp     loc_1800FB180
0x1800fb24d  xor     edx, edx
0x1800fb24f  mov     rcx, rdi
0x1800fb252  call    LdrpDecrementModuleLoadCountEx
0x1800fb257  jmp     short loc_1800FB240
0x1800fb259  lea     rdi, LdrpMscoreeDllName
0x1800fb260  xor     ebx, ebx
0x1800fb262  jmp     loc_1800FB17C
0x180167f17  push    rbp
0x180167f19  sub     rsp, 30h
0x180167f1d  mov     rbp, rdx
0x180167f20  lea     rcx, FastPebLock
0x180167f27  call    RtlLeaveCriticalSection
0x180167f2c  nop
0x180167f2d  add     rsp, 30h
0x180167f31  pop     rbp
0x180167f32  retn
```
