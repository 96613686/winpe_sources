# LdrpInitializeImportRedirection

- ea: `0x180106c24`
- end: `0x180106dc2`
- name: `LdrpInitializeImportRedirection`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x1800d6508`

## callees

- `0x18001eb80`
- `0x180023e20`
- `0x1800254e0`
- `0x1800259fc`
- `0x18002c6f0`
- `0x18004c8f0`
- `0x18004cd50`
- `0x1800bcba0`
- `0x1800e5fcc`
- `0x180106c24`
- `0x18015cbe0`
- `0x18015d5a4`
- `0x180162000`
- `0x18016f030`

## string_xrefs

- `0x180106ca4`: `Loading import redirection DLL: '%wZ'\n`

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
0x180106c24  mov     [rsp+arg_0], rbx
0x180106c29  mov     [rsp+arg_8], rsi
0x180106c2e  push    rdi
0x180106c2f  sub     rsp, 0D0h
0x180106c36  mov     rax, cs:__security_cookie
0x180106c3d  xor     rax, rsp
0x180106c40  mov     [rsp+0D8h+var_18], rax
0x180106c48  xor     edx, edx; Val
0x180106c4a  lea     rcx, [rsp+0D8h+var_98]; void *
0x180106c4f  mov     r8d, 80h; Size
0x180106c55  call    memset$thunk$772440563353939046
0x180106c5a  mov     rax, gs:60h
0x180106c63  xor     esi, esi
0x180106c65  mov     [rsp+0D8h+var_A0], rsi
0x180106c6a  mov     ebx, esi
0x180106c6c  mov     rdi, [rax+20h]
0x180106c70  add     rdi, 410h
0x180106c77  cmp     [rdi], si
0x180106c7a  jnz     short loc_180106CA4
0x180106c7c  mov     eax, ebx
0x180106c7e  mov     rcx, [rsp+0D8h+var_18]
0x180106c86  xor     rcx, rsp; StackCookie
0x180106c89  call    __security_check_cookie
0x180106c8e  lea     r11, [rsp+0D8h+var_8]
0x180106c96  mov     rbx, [r11+10h]
0x180106c9a  mov     rsi, [r11+18h]
0x180106c9e  mov     rsp, r11
0x180106ca1  pop     rdi
0x180106ca2  retn
0x180106ca4  lea     rax, aLoadingImportR; "Loading import redirection DLL: '%wZ'\n"
0x180106cab  mov     qword ptr [rsp+0D8h+ArgList], rdi; ArgList
0x180106cb0  mov     r9d, 2; int
0x180106cb6  mov     [rsp+0D8h+Format], rax; Format
0x180106cbb  lea     r8, aLdrpinitialize_4; "LdrpInitializeImportRedirection"
0x180106cc2  mov     edx, 22Dh; int
0x180106cc7  lea     rcx, aMinkernelLdrLd_8; "minkernel\\ldr\\ldrredirect.c"
0x180106cce  call    LdrpLogInternal
0x180106cd3  lea     r8, [rsp+0D8h+var_98]
0x180106cd8  xor     edx, edx
0x180106cda  xor     ecx, ecx
0x180106cdc  call    LdrpInitializeDllPath
0x180106ce1  lea     r9, [rsp+0D8h+var_A0]
0x180106ce6  mov     r8d, 1000001h
0x180106cec  lea     rdx, [rsp+0D8h+var_98]
0x180106cf1  mov     rcx, rdi; ArgList
0x180106cf4  call    LdrpLoadDll
0x180106cf9  lea     rcx, [rsp+0D8h+var_98]
0x180106cfe  mov     ebx, eax
0x180106d00  call    LdrpReleaseDllPath
0x180106d05  test    ebx, ebx
0x180106d07  js      loc_180106C7C
0x180106d0d  mov     rdi, [rsp+0D8h+var_A0]
0x180106d12  mov     rcx, rdi
0x180106d15  call    LdrpBuildImportRedirection
0x180106d1a  mov     ebx, eax
0x180106d1c  test    eax, eax
0x180106d1e  jns     short loc_180106D50
0x180106d20  mov     dword ptr [rsp+0D8h+ArgList], eax; ArgList
0x180106d24  lea     r8, aLdrpinitialize_4; "LdrpInitializeImportRedirection"
0x180106d2b  lea     rax, aUnableToBuildI; "Unable to build import redirection Tabl"...
0x180106d32  xor     r9d, r9d; int
0x180106d35  mov     edx, 248h; int
0x180106d3a  mov     [rsp+0D8h+Format], rax; Format
0x180106d3f  lea     rcx, aMinkernelLdrLd_8; "minkernel\\ldr\\ldrredirect.c"
0x180106d46  call    LdrpLogInternal
0x180106d4b  jmp     loc_180106C7C
0x180106d50  xor     ecx, ecx
0x180106d52  call    LdrpDrainWorkQueue
0x180106d57  call    LdrpAcquireLoaderLock
0x180106d5c  mov     rcx, [rdi+98h]
0x180106d63  lea     r8, [rsp+0D8h+var_A8]
0x180106d68  xor     edx, edx
0x180106d6a  mov     [rsp+0D8h+var_A8], sil
0x180106d6f  call    LdrpInitializeGraphRecurse
0x180106d74  mov     r8d, eax
0x180106d77  mov     edx, 2
0x180106d7c  mov     ebx, eax
0x180106d7e  call    LdrpReleaseLoaderLock
0x180106d83  call    LdrpDropLastInProgressCount
0x180106d88  test    ebx, ebx
0x180106d8a  js      loc_180106C7C
0x180106d90  mov     rax, [rdi+98h]
0x180106d97  mov     dword ptr [rax+18h], 0FFFFFFFFh
0x180106d9e  mov     rax, [rdi+98h]
0x180106da5  mov     rcx, [rax]
0x180106da8  mov     word ptr [rcx-34h], 0FFFFh
0x180106dae  mov     rcx, rdi
0x180106db1  call    LdrpLogImportRedirectionTelemetry
0x180106db6  mov     cs:LdrpRedirectionModule, rdi
0x180106dbd  jmp     loc_180106C7C
```
