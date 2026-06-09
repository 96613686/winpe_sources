# EtwLogNCryptKeyWrite

- ea: `0x1800202c4`
- end: `0x1800204ae`
- name: `EtwLogNCryptKeyWrite`
- size: `490`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180029004`
- `0x1800474e8`

## callees

- `0x18000d3d0`
- `0x18001aea0`
- `0x1800202c4`
- `0x1800206c8`
- `0x1800207dc`
- `0x180024260`
- `0x180038970`
- `0x180062310`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800203cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020435`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020452`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800203cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020435`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020452`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800203a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800203a3`

## pseudocode

```c
__int64 __fastcall EtwLogNCryptKeyWrite(int a1, __int64 a2, __int64 a3, char a4, int a5, int a6)
{
  int ProcessInfo; // eax
  char v11; // bl
  __int64 v12; // rdi
  unsigned int v13; // ebx
  char v15; // al
  char v16; // al
  unsigned int v17; // eax
  char CurrentThreadId; // al
  unsigned int v19; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp-88h] BYREF
  __int64 v21; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v22[528]; // [rsp+90h] [rbp-70h] BYREF

  v19 = 0;
  v21 = 0;
  hMem = 0;
  memset_0(v22, 0, 0x208u);
  ProcessInfo = I_GetProcessInfo(&v19, &v21);
  v11 = v19;
  if ( !ProcessInfo )
    I_GetServiceTag(v19, 260, v22);
  I_GetUserId((LPWSTR *)&hMem);
  v12 = v21;
  if ( a6 )
  {
    if ( (Microsoft_Windows_Crypto_NCryptEnableBits & 1) == 0 )
    {
LABEL_5:
      v13 = 0;
      goto LABEL_6;
    }
    CurrentThreadId = GetCurrentThreadId();
    v17 = McTemplateU0zddzzzddzzd_EventWriteTransfer(
            (_DWORD)hMem,
            (unsigned int)ETW_LOG_NCRYPT_KEY_WRITE_FAILED,
            a1,
            a5,
            a4,
            a2,
            a3,
            v12,
            v11,
            CurrentThreadId,
            (__int64)hMem,
            (__int64)v22,
            a6);
  }
  else
  {
    if ( (Microsoft_Windows_Crypto_NCryptEnableBits & 4) != 0 )
    {
      v15 = GetCurrentThreadId();
      McTemplateU0zddzzzddzzd_EventWriteTransfer(
        (_DWORD)hMem,
        (unsigned int)ETW_LOG_NCRYPT_KEY_WRITE_SUCCEEDED,
        a1,
        a5,
        a4,
        a2,
        a3,
        v12,
        v11,
        v15,
        (__int64)hMem,
        (__int64)v22,
        0);
    }
    if ( (byte_18007A101 & 4) == 0 )
      goto LABEL_5;
    v16 = GetCurrentThreadId();
    v17 = McTemplateU0zddzzzddzzd_EventWriteTransfer(
            (_DWORD)hMem,
            (unsigned int)ETW_LOG_KEYMGMT_NCRYPT_WRITE_KEY_SUCCEEDED,
            a1,
            a5,
            a4,
            a2,
            a3,
            v12,
            v11,
            v16,
            (__int64)hMem,
            (__int64)v22,
            0);
  }
  v13 = v17;
LABEL_6:
  if ( v12 )
    MSCryptFree(v12);
  if ( hMem )
    LocalFree(hMem);
  return v13;
}

```

## disassembly

```asm
0x1800202c4  mov     [rsp-8+arg_18], rbx
0x1800202c9  push    rbp
0x1800202ca  push    rsi
0x1800202cb  push    rdi
0x1800202cc  push    r12
0x1800202ce  push    r13
0x1800202d0  push    r14
0x1800202d2  push    r15
0x1800202d4  lea     rbp, [rsp-1B0h]
0x1800202dc  sub     rsp, 2B0h
0x1800202e3  mov     rax, cs:__security_cookie
0x1800202ea  xor     rax, rsp
0x1800202ed  mov     [rbp+1E0h+var_40], rax
0x1800202f4  xor     edi, edi
0x1800202f6  mov     r13, r8
0x1800202f9  mov     r12, rdx
0x1800202fc  mov     [rsp+2E0h+var_270], edi
0x180020300  mov     r15, rcx
0x180020303  mov     [rbp+1E0h+var_260], rdi
0x180020307  xor     edx, edx; Val
0x180020309  mov     [rsp+2E0h+hMem], rdi
0x18002030e  mov     r8d, 208h; Size
0x180020314  lea     rcx, [rbp+1E0h+var_250]; void *
0x180020318  mov     r14d, r9d
0x18002031b  call    memset_0
0x180020320  lea     rdx, [rbp+1E0h+var_260]
0x180020324  lea     rcx, [rsp+2E0h+var_270]
0x180020329  call    I_GetProcessInfo
0x18002032e  mov     ebx, [rsp+2E0h+var_270]
0x180020332  test    eax, eax
0x180020334  jz      short loc_1800203B1
0x180020336  lea     rcx, [rsp+2E0h+hMem]; StringSid
0x18002033b  call    I_GetUserId
0x180020340  mov     esi, [rbp+1E0h+arg_28]
0x180020346  mov     rdi, [rbp+1E0h+var_260]
0x18002034a  test    esi, esi
0x18002034c  jz      short loc_1800203C6
0x18002034e  test    cs:Microsoft_Windows_Crypto_NCryptEnableBits, 1
0x180020355  jnz     loc_180020452
0x18002035b  xor     ebx, ebx
0x18002035d  test    rdi, rdi
0x180020360  jnz     short loc_180020399
0x180020362  mov     rcx, [rsp+2E0h+hMem]; hMem
0x180020367  test    rcx, rcx
0x18002036a  jnz     short loc_1800203A3
0x18002036c  mov     eax, ebx
0x18002036e  mov     rcx, [rbp+1E0h+var_40]
0x180020375  xor     rcx, rsp; StackCookie
0x180020378  call    __security_check_cookie
0x18002037d  mov     rbx, [rsp+2E0h+arg_18]
0x180020385  add     rsp, 2B0h
0x18002038c  pop     r15
0x18002038e  pop     r14
0x180020390  pop     r13
0x180020392  pop     r12
0x180020394  pop     rdi
0x180020395  pop     rsi
0x180020396  pop     rbp
0x180020397  retn
0x180020399  mov     rcx, rdi
0x18002039c  call    MSCryptFree
0x1800203a1  jmp     short loc_180020362
0x1800203a3  call    cs:__imp_LocalFree
0x1800203aa  nop     dword ptr [rax+rax+00h]
0x1800203af  jmp     short loc_18002036C
0x1800203b1  mov     edx, 104h
0x1800203b6  lea     r8, [rbp+1E0h+var_250]
0x1800203ba  mov     ecx, ebx
0x1800203bc  call    I_GetServiceTag
0x1800203c1  jmp     loc_180020336
0x1800203c6  test    cs:Microsoft_Windows_Crypto_NCryptEnableBits, 4
0x1800203cd  jz      short loc_180020428
0x1800203cf  call    cs:__imp_GetCurrentThreadId
0x1800203d6  nop     dword ptr [rax+rax+00h]
0x1800203db  mov     r9d, [rbp+1E0h+arg_20]
0x1800203e2  lea     rcx, [rbp+1E0h+var_250]
0x1800203e6  mov     [rsp+2E0h+var_280], 0
0x1800203ee  lea     rdx, ETW_LOG_NCRYPT_KEY_WRITE_SUCCEEDED
0x1800203f5  mov     [rsp+2E0h+var_288], rcx
0x1800203fa  mov     r8, r15
0x1800203fd  mov     rcx, [rsp+2E0h+hMem]
0x180020402  mov     [rsp+2E0h+var_290], rcx
0x180020407  mov     [rsp+2E0h+var_298], eax
0x18002040b  mov     [rsp+2E0h+var_2A0], ebx
0x18002040f  mov     [rsp+2E0h+var_2A8], rdi
0x180020414  mov     [rsp+2E0h+var_2B0], r13
0x180020419  mov     [rsp+2E0h+var_2B8], r12
0x18002041e  mov     [rsp+2E0h+var_2C0], r14d
0x180020423  call    McTemplateU0zddzzzddzzd_EventWriteTransfer
0x180020428  test    cs:byte_18007A101, 4
0x18002042f  jz      loc_18002035B
0x180020435  call    cs:__imp_GetCurrentThreadId
0x18002043c  nop     dword ptr [rax+rax+00h]
0x180020441  lea     rdx, ETW_LOG_KEYMGMT_NCRYPT_WRITE_KEY_SUCCEEDED
0x180020448  mov     [rsp+2E0h+var_280], 0
0x180020450  jmp     short loc_180020469
0x180020452  call    cs:__imp_GetCurrentThreadId
0x180020459  nop     dword ptr [rax+rax+00h]
0x18002045e  lea     rdx, ETW_LOG_NCRYPT_KEY_WRITE_FAILED
0x180020465  mov     [rsp+2E0h+var_280], esi
0x180020469  mov     r9d, [rbp+1E0h+arg_20]
0x180020470  lea     rcx, [rbp+1E0h+var_250]
0x180020474  mov     [rsp+2E0h+var_288], rcx
0x180020479  mov     r8, r15
0x18002047c  mov     rcx, [rsp+2E0h+hMem]
0x180020481  mov     [rsp+2E0h+var_290], rcx
0x180020486  mov     [rsp+2E0h+var_298], eax
0x18002048a  mov     [rsp+2E0h+var_2A0], ebx
0x18002048e  mov     [rsp+2E0h+var_2A8], rdi
0x180020493  mov     [rsp+2E0h+var_2B0], r13
0x180020498  mov     [rsp+2E0h+var_2B8], r12
0x18002049d  mov     [rsp+2E0h+var_2C0], r14d
0x1800204a2  call    McTemplateU0zddzzzddzzd_EventWriteTransfer
0x1800204a7  mov     ebx, eax
0x1800204a9  jmp     loc_18002035D
```
