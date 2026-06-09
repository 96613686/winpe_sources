# LdrpInitializeImportRedirection

- ea: `0x180107a54`
- end: `0x180107bf2`
- name: `LdrpInitializeImportRedirection`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x180050718`

## callees

- `0x18001eb80`
- `0x180023e10`
- `0x1800254d0`
- `0x1800259ec`
- `0x18002b9f0`
- `0x1800694f0`
- `0x180069950`
- `0x1800c0e80`
- `0x1800e634c`
- `0x180107a54`
- `0x18015d3f0`
- `0x18015ddb4`
- `0x180162810`
- `0x18016f030`

## string_xrefs

- `0x180107ad4`: `Loading import redirection DLL: '%wZ'\n`

## pseudocode

```c
__int64 LdrpInitializeImportRedirection()
{
  __int64 v0; // rbx
  _UNICODE_STRING *ArgList; // rdi
  __int64 v3; // rdi
  int v4; // eax
  __int64 v5; // rcx
  __int64 v6; // rcx
  _BYTE v7[8]; // [rsp+30h] [rbp-A8h] BYREF
  __int64 v8; // [rsp+38h] [rbp-A0h] BYREF
  __int64 v9[16]; // [rsp+40h] [rbp-98h] BYREF

  memset_thunk_772440563353939046(v9, 0, 0x80u);
  v8 = 0;
  LODWORD(v0) = 0;
  ArgList = &NtCurrentPeb()->ProcessParameters->RedirectionDllName;
  if ( ArgList->Length )
  {
    LdrpLogInternal(
      (int)"minkernel\\ldr\\ldrredirect.c",
      557,
      (int)"LdrpInitializeImportRedirection",
      2,
      "Loading import redirection DLL: '%wZ'\n",
      (char)ArgList);
    LdrpInitializeDllPath(0, 0, v9);
    LODWORD(v0) = LdrpLoadDll(&ArgList->Length, (__int64)v9, 0x1000001u, (__int64)&v8);
    LdrpReleaseDllPath(v9);
    if ( (int)v0 >= 0 )
    {
      v3 = v8;
      v4 = LdrpBuildImportRedirection(v8);
      LODWORD(v0) = v4;
      if ( v4 >= 0 )
      {
        LdrpDrainWorkQueue(0);
        LdrpAcquireLoaderLock();
        v5 = *(_QWORD *)(v3 + 152);
        v7[0] = 0;
        v0 = (unsigned int)LdrpInitializeGraphRecurse(v5, 0, v7);
        LdrpReleaseLoaderLock(v6, 2, v0);
        LdrpDropLastInProgressCount();
        if ( (int)v0 >= 0 )
        {
          *(_DWORD *)(*(_QWORD *)(v3 + 152) + 24LL) = -1;
          *(_WORD *)(**(_QWORD **)(v3 + 152) - 52LL) = -1;
          LdrpLogImportRedirectionTelemetry(v3);
          LdrpRedirectionModule = v3;
        }
      }
      else
      {
        LdrpLogInternal(
          (int)"minkernel\\ldr\\ldrredirect.c",
          584,
          (int)"LdrpInitializeImportRedirection",
          0,
          "Unable to build import redirection Table, Status = 0x%x\n",
          v4);
      }
    }
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x180107a54  mov     [rsp+arg_0], rbx
0x180107a59  mov     [rsp+arg_8], rsi
0x180107a5e  push    rdi
0x180107a5f  sub     rsp, 0D0h
0x180107a66  mov     rax, cs:__security_cookie
0x180107a6d  xor     rax, rsp
0x180107a70  mov     [rsp+0D8h+var_18], rax
0x180107a78  xor     edx, edx; Val
0x180107a7a  lea     rcx, [rsp+0D8h+var_98]; void *
0x180107a7f  mov     r8d, 80h; Size
0x180107a85  call    memset$thunk$772440563353939046
0x180107a8a  mov     rax, gs:60h
0x180107a93  xor     esi, esi
0x180107a95  mov     [rsp+0D8h+var_A0], rsi
0x180107a9a  mov     ebx, esi
0x180107a9c  mov     rdi, [rax+20h]
0x180107aa0  add     rdi, 410h
0x180107aa7  cmp     [rdi], si
0x180107aaa  jnz     short loc_180107AD4
0x180107aac  mov     eax, ebx
0x180107aae  mov     rcx, [rsp+0D8h+var_18]
0x180107ab6  xor     rcx, rsp; StackCookie
0x180107ab9  call    __security_check_cookie
0x180107abe  lea     r11, [rsp+0D8h+var_8]
0x180107ac6  mov     rbx, [r11+10h]
0x180107aca  mov     rsi, [r11+18h]
0x180107ace  mov     rsp, r11
0x180107ad1  pop     rdi
0x180107ad2  retn
0x180107ad4  lea     rax, aLoadingImportR; "Loading import redirection DLL: '%wZ'\n"
0x180107adb  mov     qword ptr [rsp+0D8h+ArgList], rdi; ArgList
0x180107ae0  mov     r9d, 2; int
0x180107ae6  mov     [rsp+0D8h+Format], rax; Format
0x180107aeb  lea     r8, aLdrpinitialize_4; "LdrpInitializeImportRedirection"
0x180107af2  mov     edx, 22Dh; int
0x180107af7  lea     rcx, aMinkernelLdrLd_8; "minkernel\\ldr\\ldrredirect.c"
0x180107afe  call    LdrpLogInternal
0x180107b03  lea     r8, [rsp+0D8h+var_98]
0x180107b08  xor     edx, edx
0x180107b0a  xor     ecx, ecx
0x180107b0c  call    LdrpInitializeDllPath
0x180107b11  lea     r9, [rsp+0D8h+var_A0]
0x180107b16  mov     r8d, 1000001h
0x180107b1c  lea     rdx, [rsp+0D8h+var_98]
0x180107b21  mov     rcx, rdi; ArgList
0x180107b24  call    LdrpLoadDll
0x180107b29  lea     rcx, [rsp+0D8h+var_98]
0x180107b2e  mov     ebx, eax
0x180107b30  call    LdrpReleaseDllPath
0x180107b35  test    ebx, ebx
0x180107b37  js      loc_180107AAC
0x180107b3d  mov     rdi, [rsp+0D8h+var_A0]
0x180107b42  mov     rcx, rdi
0x180107b45  call    LdrpBuildImportRedirection
0x180107b4a  mov     ebx, eax
0x180107b4c  test    eax, eax
0x180107b4e  jns     short loc_180107B80
0x180107b50  mov     dword ptr [rsp+0D8h+ArgList], eax; ArgList
0x180107b54  lea     r8, aLdrpinitialize_4; "LdrpInitializeImportRedirection"
0x180107b5b  lea     rax, aUnableToBuildI; "Unable to build import redirection Tabl"...
0x180107b62  xor     r9d, r9d; int
0x180107b65  mov     edx, 248h; int
0x180107b6a  mov     [rsp+0D8h+Format], rax; Format
0x180107b6f  lea     rcx, aMinkernelLdrLd_8; "minkernel\\ldr\\ldrredirect.c"
0x180107b76  call    LdrpLogInternal
0x180107b7b  jmp     loc_180107AAC
0x180107b80  xor     ecx, ecx
0x180107b82  call    LdrpDrainWorkQueue
0x180107b87  call    LdrpAcquireLoaderLock
0x180107b8c  mov     rcx, [rdi+98h]
0x180107b93  lea     r8, [rsp+0D8h+var_A8]
0x180107b98  xor     edx, edx
0x180107b9a  mov     [rsp+0D8h+var_A8], sil
0x180107b9f  call    LdrpInitializeGraphRecurse
0x180107ba4  mov     r8d, eax
0x180107ba7  mov     edx, 2
0x180107bac  mov     ebx, eax
0x180107bae  call    LdrpReleaseLoaderLock
0x180107bb3  call    LdrpDropLastInProgressCount
0x180107bb8  test    ebx, ebx
0x180107bba  js      loc_180107AAC
0x180107bc0  mov     rax, [rdi+98h]
0x180107bc7  mov     dword ptr [rax+18h], 0FFFFFFFFh
0x180107bce  mov     rax, [rdi+98h]
0x180107bd5  mov     rcx, [rax]
0x180107bd8  mov     word ptr [rcx-34h], 0FFFFh
0x180107bde  mov     rcx, rdi
0x180107be1  call    LdrpLogImportRedirectionTelemetry
0x180107be6  mov     cs:LdrpRedirectionModule, rdi
0x180107bed  jmp     loc_180107AAC
```
