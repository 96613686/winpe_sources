# LdrpCorInitialize

- ea: `0x1800fbd9c`
- end: `0x1800fbfa7`
- name: `LdrpCorInitialize`
- size: `523`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180050718`

## callees

- `0x18001d490`
- `0x18001e820`
- `0x180023e10`
- `0x180024ea0`
- `0x18002b9f0`
- `0x18006ffa0`
- `0x180070490`
- `0x1800709e0`
- `0x18009a6b0`
- `0x1800fbd9c`
- `0x1800fbfb0`
- `0x180162810`
- `0x18016f030`

## string_xrefs

- `0x1800fbe2e`: `COMPLUS_InstallRoot`
- `0x1800fbe5f`: `COMPLUS_Version`

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
0x1800fbd9c  mov     [rsp+arg_8], rbx
0x1800fbda1  mov     [rsp+arg_10], rsi
0x1800fbda6  push    rdi
0x1800fbda7  sub     rsp, 1F0h
0x1800fbdae  mov     rax, cs:__security_cookie
0x1800fbdb5  xor     rax, rsp
0x1800fbdb8  mov     [rsp+1F8h+var_18], rax
0x1800fbdc0  mov     rsi, rcx
0x1800fbdc3  mov     [rsp+1F8h+var_1B8], 0
0x1800fbdcc  xor     edx, edx; Val
0x1800fbdce  mov     r8d, 80h; Size
0x1800fbdd4  lea     rcx, [rsp+1F8h+var_98]; void *
0x1800fbddc  call    memset$thunk$772440563353939046
0x1800fbde1  mov     bl, 1
0x1800fbde3  mov     [rsp+1F8h+var_1C0], 0
0x1800fbdec  xor     edx, edx; Val
0x1800fbdee  mov     r8d, 110h; Size
0x1800fbdf4  lea     rcx, [rsp+1F8h+ArgList]; void *
0x1800fbdf9  call    memset$thunk$772440563353939046
0x1800fbdfe  mov     [rsp+1F8h+var_1C8], 0
0x1800fbe07  lea     rcx, FastPebLock
0x1800fbe0e  call    RtlEnterCriticalSection
0x1800fbe13  nop
0x1800fbe14  lea     rax, [rsp+1F8h+var_1C8]
0x1800fbe19  mov     [rsp+1F8h+var_1D0], rax
0x1800fbe1e  mov     [rsp+1F8h+var_1D8], 0
0x1800fbe27  xor     r9d, r9d
0x1800fbe2a  lea     r8d, [r9+13h]
0x1800fbe2e  lea     rdx, LdrpComPlusInstallRootName; "COMPLUS_InstallRoot"
0x1800fbe35  xor     ecx, ecx
0x1800fbe37  call    RtlQueryEnvironmentVariable
0x1800fbe3c  mov     edi, 0C0000023h
0x1800fbe41  cmp     eax, edi
0x1800fbe43  jnz     short loc_1800FBE77
0x1800fbe45  lea     rax, [rsp+1F8h+var_1C8]
0x1800fbe4a  mov     [rsp+1F8h+var_1D0], rax
0x1800fbe4f  mov     [rsp+1F8h+var_1D8], 0
0x1800fbe58  xor     r9d, r9d
0x1800fbe5b  lea     r8d, [r9+0Fh]
0x1800fbe5f  lea     rdx, LdrpComPlusVersionName; "COMPLUS_Version"
0x1800fbe66  xor     ecx, ecx
0x1800fbe68  call    RtlQueryEnvironmentVariable
0x1800fbe6d  movzx   ebx, bl
0x1800fbe70  xor     edx, edx
0x1800fbe72  cmp     eax, edi
0x1800fbe74  cmovz   ebx, edx
0x1800fbe77  lea     rcx, FastPebLock
0x1800fbe7e  call    RtlLeaveCriticalSection
0x1800fbe83  lea     rax, [rsp+1F8h+var_198]
0x1800fbe88  mov     [rsp+1F8h+var_1A0], rax
0x1800fbe8d  mov     dword ptr [rsp+1F8h+ArgList], 1000000h
0x1800fbe95  xor     eax, eax
0x1800fbe97  mov     [rsp+1F8h+var_198], ax
0x1800fbe9c  test    bl, bl
0x1800fbe9e  jz      loc_1800FBF99
0x1800fbea4  lea     rdx, LdrpMscoreeDllName
0x1800fbeab  lea     rcx, [rsp+1F8h+ArgList]
0x1800fbeb0  call    LdrpBuildSystem32FileName
0x1800fbeb5  mov     ebx, eax
0x1800fbeb7  lea     rdi, [rsp+1F8h+ArgList]
0x1800fbebc  test    ebx, ebx
0x1800fbebe  jns     short loc_1800FBEFC
0x1800fbec0  lea     rax, [rsp+1F8h+var_198]
0x1800fbec5  mov     rcx, [rsp+1F8h+var_1A0]
0x1800fbeca  cmp     rax, rcx
0x1800fbecd  jz      short loc_1800FBED4
0x1800fbecf  call    RtlpSysVolFree
0x1800fbed4  mov     eax, ebx
0x1800fbed6  mov     rcx, [rsp+1F8h+var_18]
0x1800fbede  xor     rcx, rsp; StackCookie
0x1800fbee1  call    __security_check_cookie
0x1800fbee6  lea     r11, [rsp+1F8h+var_8]
0x1800fbeee  mov     rbx, [r11+18h]
0x1800fbef2  mov     rsi, [r11+20h]
0x1800fbef6  mov     rsp, r11
0x1800fbef9  pop     rdi
0x1800fbefa  retn
0x1800fbefc  xor     edx, edx; Val
0x1800fbefe  mov     r8d, 80h; Size
0x1800fbf04  lea     rcx, [rsp+1F8h+var_98]; void *
0x1800fbf0c  call    memset$thunk$772440563353939046
0x1800fbf11  lea     r9, [rsp+1F8h+var_1C0]
0x1800fbf16  mov     r8d, 1
0x1800fbf1c  lea     rdx, [rsp+1F8h+var_98]
0x1800fbf24  mov     rcx, rdi; ArgList
0x1800fbf27  call    LdrpLoadDll
0x1800fbf2c  mov     ebx, eax
0x1800fbf2e  lea     rcx, [rsp+1F8h+var_98]
0x1800fbf36  call    LdrpReleaseDllPath
0x1800fbf3b  test    ebx, ebx
0x1800fbf3d  js      short loc_1800FBEC0
0x1800fbf3f  lea     r9, [rsp+1F8h+var_1B8]
0x1800fbf44  xor     r8d, r8d
0x1800fbf47  lea     rdx, aCorexemain; "_CorExeMain"
0x1800fbf4e  mov     rdi, [rsp+1F8h+var_1C0]
0x1800fbf53  mov     rcx, [rdi+30h]
0x1800fbf57  call    LdrpGetProcedureAddress
0x1800fbf5c  mov     ebx, eax
0x1800fbf5e  test    eax, eax
0x1800fbf60  js      short loc_1800FBF8D
0x1800fbf62  mov     eax, ds:7FFE0330h
0x1800fbf69  mov     ecx, eax
0x1800fbf6b  and     ecx, 3Fh
0x1800fbf6e  xor     rax, [rsp+1F8h+var_1B8]
0x1800fbf73  ror     rax, cl
0x1800fbf76  mov     cs:LdrpCorExeMainRoutine, rax
0x1800fbf7d  mov     [rsi], rdi
0x1800fbf80  mov     rcx, rdi
0x1800fbf83  call    LdrpDereferenceModule
0x1800fbf88  jmp     loc_1800FBEC0
0x1800fbf8d  xor     edx, edx
0x1800fbf8f  mov     rcx, rdi
0x1800fbf92  call    LdrpDecrementModuleLoadCountEx
0x1800fbf97  jmp     short loc_1800FBF80
0x1800fbf99  lea     rdi, LdrpMscoreeDllName
0x1800fbfa0  xor     ebx, ebx
0x1800fbfa2  jmp     loc_1800FBEBC
0x180168737  push    rbp
0x180168739  sub     rsp, 30h
0x18016873d  mov     rbp, rdx
0x180168740  lea     rcx, FastPebLock
0x180168747  call    RtlLeaveCriticalSection
0x18016874c  nop
0x18016874d  add     rsp, 30h
0x180168751  pop     rbp
0x180168752  retn
```
