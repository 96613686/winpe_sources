# EtwLogNCryptDeleteKey

- ea: `0x1800204b4`
- end: `0x1800206c2`
- name: `EtwLogNCryptDeleteKey`
- size: `526`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003770`
- `0x18000ed10`

## callees

- `0x18000d3d0`
- `0x18001aea0`
- `0x1800204b4`
- `0x1800206c8`
- `0x1800207dc`
- `0x180024260`
- `0x180038970`
- `0x180062310`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800205b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002061a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020665`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800205b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002061a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020665`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020587`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020587`

## pseudocode

```c
__int64 __fastcall EtwLogNCryptDeleteKey(int a1, __int64 a2, __int64 a3, int a4, char a5, int a6)
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
            (unsigned int)ETW_LOG_NCRYPT_DELETE_KEY_FAILED,
            a1,
            a4,
            a5,
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
        (unsigned int)ETW_LOG_NCRYPT_DELETE_KEY_SUCCEEDED,
        a1,
        a4,
        a5,
        a2,
        a3,
        v12,
        v11,
        v15,
        (__int64)hMem,
        (__int64)v22,
        0);
    }
    if ( (byte_18007A101 & 8) == 0 )
      goto LABEL_5;
    v16 = GetCurrentThreadId();
    v17 = McTemplateU0zddzzzddzzd_EventWriteTransfer(
            (_DWORD)hMem,
            (unsigned int)ETW_LOG_KEYMGMT_NCRYPT_DELETE_KEY_SUCCEEDED,
            a1,
            a4,
            a5,
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
0x1800204b4  push    rbp
0x1800204b6  push    rbx
0x1800204b7  push    rsi
0x1800204b8  push    rdi
0x1800204b9  push    r12
0x1800204bb  push    r13
0x1800204bd  push    r14
0x1800204bf  push    r15
0x1800204c1  lea     rbp, [rsp-1B8h]
0x1800204c9  sub     rsp, 2B8h
0x1800204d0  mov     rax, cs:__security_cookie
0x1800204d7  xor     rax, rsp
0x1800204da  mov     [rbp+1F0h+var_50], rax
0x1800204e1  xor     edi, edi
0x1800204e3  mov     r12, r8
0x1800204e6  mov     r15, rdx
0x1800204e9  mov     [rsp+2F0h+var_280], edi
0x1800204ed  mov     r14, rcx
0x1800204f0  mov     [rbp+1F0h+var_270], rdi
0x1800204f4  xor     edx, edx; Val
0x1800204f6  mov     [rsp+2F0h+hMem], rdi
0x1800204fb  mov     r8d, 208h; Size
0x180020501  lea     rcx, [rbp+1F0h+var_260]; void *
0x180020505  mov     r13d, r9d
0x180020508  call    memset_0
0x18002050d  lea     rdx, [rbp+1F0h+var_270]
0x180020511  lea     rcx, [rsp+2F0h+var_280]
0x180020516  call    I_GetProcessInfo
0x18002051b  mov     ebx, [rsp+2F0h+var_280]
0x18002051f  test    eax, eax
0x180020521  jz      short loc_180020595
0x180020523  lea     rcx, [rsp+2F0h+hMem]; StringSid
0x180020528  call    I_GetUserId
0x18002052d  mov     esi, [rbp+1F0h+arg_28]
0x180020533  mov     rdi, [rbp+1F0h+var_270]
0x180020537  test    esi, esi
0x180020539  jz      short loc_1800205AA
0x18002053b  test    cs:Microsoft_Windows_Crypto_NCryptEnableBits, 1
0x180020542  jnz     loc_180020665
0x180020548  xor     ebx, ebx
0x18002054a  test    rdi, rdi
0x18002054d  jz      short loc_180020557
0x18002054f  mov     rcx, rdi
0x180020552  call    MSCryptFree
0x180020557  mov     rcx, [rsp+2F0h+hMem]; hMem
0x18002055c  test    rcx, rcx
0x18002055f  jnz     short loc_180020587
0x180020561  mov     eax, ebx
0x180020563  mov     rcx, [rbp+1F0h+var_50]
0x18002056a  xor     rcx, rsp; StackCookie
0x18002056d  call    __security_check_cookie
0x180020572  add     rsp, 2B8h
0x180020579  pop     r15
0x18002057b  pop     r14
0x18002057d  pop     r13
0x18002057f  pop     r12
0x180020581  pop     rdi
0x180020582  pop     rsi
0x180020583  pop     rbx
0x180020584  pop     rbp
0x180020585  retn
0x180020587  call    cs:__imp_LocalFree
0x18002058e  nop     dword ptr [rax+rax+00h]
0x180020593  jmp     short loc_180020561
0x180020595  mov     edx, 104h
0x18002059a  lea     r8, [rbp+1F0h+var_260]
0x18002059e  mov     ecx, ebx
0x1800205a0  call    I_GetServiceTag
0x1800205a5  jmp     loc_180020523
0x1800205aa  test    cs:Microsoft_Windows_Crypto_NCryptEnableBits, 4
0x1800205b1  mov     esi, dword ptr [rbp+1F0h+arg_20]
0x1800205b7  jz      short loc_18002060D
0x1800205b9  call    cs:__imp_GetCurrentThreadId
0x1800205c0  nop     dword ptr [rax+rax+00h]
0x1800205c5  mov     [rsp+2F0h+var_290], 0
0x1800205cd  lea     rcx, [rbp+1F0h+var_260]
0x1800205d1  mov     [rsp+2F0h+var_298], rcx
0x1800205d6  lea     rdx, ETW_LOG_NCRYPT_DELETE_KEY_SUCCEEDED
0x1800205dd  mov     rcx, [rsp+2F0h+hMem]
0x1800205e2  mov     r9d, r13d
0x1800205e5  mov     [rsp+2F0h+var_2A0], rcx
0x1800205ea  mov     r8, r14
0x1800205ed  mov     [rsp+2F0h+var_2A8], eax
0x1800205f1  mov     [rsp+2F0h+var_2B0], ebx
0x1800205f5  mov     [rsp+2F0h+var_2B8], rdi
0x1800205fa  mov     [rsp+2F0h+var_2C0], r12
0x1800205ff  mov     [rsp+2F0h+var_2C8], r15
0x180020604  mov     [rsp+2F0h+var_2D0], esi
0x180020608  call    McTemplateU0zddzzzddzzd_EventWriteTransfer
0x18002060d  test    cs:byte_18007A101, 8
0x180020614  jz      loc_180020548
0x18002061a  call    cs:__imp_GetCurrentThreadId
0x180020621  nop     dword ptr [rax+rax+00h]
0x180020626  mov     [rsp+2F0h+var_290], 0
0x18002062e  lea     rcx, [rbp+1F0h+var_260]
0x180020632  mov     [rsp+2F0h+var_298], rcx
0x180020637  lea     rdx, ETW_LOG_KEYMGMT_NCRYPT_DELETE_KEY_SUCCEEDED
0x18002063e  mov     rcx, [rsp+2F0h+hMem]
0x180020643  mov     [rsp+2F0h+var_2A0], rcx
0x180020648  mov     [rsp+2F0h+var_2A8], eax
0x18002064c  mov     [rsp+2F0h+var_2B0], ebx
0x180020650  mov     [rsp+2F0h+var_2B8], rdi
0x180020655  mov     [rsp+2F0h+var_2C0], r12
0x18002065a  mov     [rsp+2F0h+var_2C8], r15
0x18002065f  mov     [rsp+2F0h+var_2D0], esi
0x180020663  jmp     short loc_1800206B0
0x180020665  call    cs:__imp_GetCurrentThreadId
0x18002066c  nop     dword ptr [rax+rax+00h]
0x180020671  mov     [rsp+2F0h+var_290], esi
0x180020675  lea     rcx, [rbp+1F0h+var_260]
0x180020679  mov     [rsp+2F0h+var_298], rcx
0x18002067e  lea     rdx, ETW_LOG_NCRYPT_DELETE_KEY_FAILED
0x180020685  mov     rcx, [rsp+2F0h+hMem]
0x18002068a  mov     [rsp+2F0h+var_2A0], rcx
0x18002068f  mov     [rsp+2F0h+var_2A8], eax
0x180020693  mov     eax, dword ptr [rbp+1F0h+arg_20]
0x180020699  mov     [rsp+2F0h+var_2B0], ebx
0x18002069d  mov     [rsp+2F0h+var_2B8], rdi
0x1800206a2  mov     [rsp+2F0h+var_2C0], r12
0x1800206a7  mov     [rsp+2F0h+var_2C8], r15
0x1800206ac  mov     [rsp+2F0h+var_2D0], eax
0x1800206b0  mov     r9d, r13d
0x1800206b3  mov     r8, r14
0x1800206b6  call    McTemplateU0zddzzzddzzd_EventWriteTransfer
0x1800206bb  mov     ebx, eax
0x1800206bd  jmp     loc_18002054A
```
