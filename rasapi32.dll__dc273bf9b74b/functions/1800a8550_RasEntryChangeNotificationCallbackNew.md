# RasEntryChangeNotificationCallbackNew

- ea: `0x1800a8550`
- end: `0x1800a87a5`
- name: `RasEntryChangeNotificationCallbackNew`
- size: `597`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180010d10`
- `0x18004e580`
- `0x18004e984`
- `0x18007f140`
- `0x1800a8550`
- `0x1800a87ac`
- `0x1800a8910`
- `0x1800ded06`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x1800a8696`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadStackGuarantee` at `0x1800a8696`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a86bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a86bb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800a8721`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800a8721`

## pseudocode

```c
void __fastcall RasEntryChangeNotificationCallbackNew(
        PTP_CALLBACK_INSTANCE Instance,
        unsigned int *Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  __int64 v7; // rdx
  __int64 v8; // r8
  int v9; // eax
  int v10; // edx
  int v11; // r8d
  __int64 v12; // rbx
  DWORD LastError; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  _DWORD v16[76]; // [rsp+40h] [rbp-E98h] BYREF
  _BYTE v17[514]; // [rsp+170h] [rbp-D68h] BYREF
  _BYTE v18[2918]; // [rsp+372h] [rbp-B66h] BYREF
  ULONG StackSizeInBytes; // [rsp+EE8h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, WPP_a576594392393f475090d0b18cfbf556_Traceguids);
  }
  StackSizeInBytes = 0x10000;
  memset_0(v16, 0, 0xE60u);
  DebugInit();
  if ( Context && *((_QWORD *)Context + 4) )
  {
    if ( WaitResult == 128 || WaitResult == 258 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Dl(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, v8, *Context, WaitResult);
      }
    }
    else
    {
      v9 = ((__int64 (__fastcall *)(_QWORD, _DWORD *))g_pRasGetNotificationEntry)(*Context, v16);
      if ( v9 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            92,
            WPP_a576594392393f475090d0b18cfbf556_Traceguids,
            *Context,
            v9);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_lSSD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, v16[0], (__int64)v18, (__int64)v17, *Context);
        }
        if ( !SetThreadStackGuarantee(&StackSizeInBytes)
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          v12 = *((_QWORD *)WPP_GLOBAL_Control + 2);
          LastError = GetLastError();
          WPP_SF_d(v12, 94, WPP_a576594392393f475090d0b18cfbf556_Traceguids, LastError);
        }
        (*((void (__fastcall **)(_QWORD, _QWORD, _DWORD *, __int64))Context + 3))(0, *((_QWORD *)Context + 4), v16, 1);
      }
    }
    SetThreadpoolWait(Wait, *((HANDLE *)Context + 1), 0);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      v15 = 95;
LABEL_40:
      WPP_SF_(v14[2], v15, WPP_a576594392393f475090d0b18cfbf556_Traceguids);
    }
  }
  else
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, WPP_a576594392393f475090d0b18cfbf556_Traceguids);
        v14 = WPP_GLOBAL_Control;
      }
      if ( v14 != &WPP_GLOBAL_Control && (*((_DWORD *)v14 + 7) & 0x800) != 0 && *((_BYTE *)v14 + 25) >= 6u )
      {
        v15 = 90;
        goto LABEL_40;
      }
    }
  }
}

```

## disassembly

```asm
0x1800a8550  push    rbx
0x1800a8552  push    rbp
0x1800a8553  push    rsi
0x1800a8554  push    rdi
0x1800a8555  push    r14
0x1800a8557  push    r15
0x1800a8559  sub     rsp, 0EA8h
0x1800a8560  mov     ebx, r9d
0x1800a8563  mov     rsi, r8
0x1800a8566  mov     rdi, rdx
0x1800a8569  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a8570  lea     r14, WPP_GLOBAL_Control
0x1800a8577  lea     r15, WPP_a576594392393f475090d0b18cfbf556_Traceguids
0x1800a857e  mov     ebp, 800h
0x1800a8583  cmp     rcx, r14
0x1800a8586  jz      short loc_1800A85A4
0x1800a8588  test    [rcx+1Ch], ebp
0x1800a858b  jz      short loc_1800A85A4
0x1800a858d  cmp     byte ptr [rcx+19h], 6
0x1800a8591  jb      short loc_1800A85A4
0x1800a8593  mov     rcx, [rcx+10h]
0x1800a8597  mov     edx, 58h ; 'X'
0x1800a859c  mov     r8, r15
0x1800a859f  call    WPP_SF_
0x1800a85a4  xor     edx, edx; Val
0x1800a85a6  mov     [rsp+0ED8h+StackSizeInBytes], 10000h
0x1800a85b1  mov     r8d, 0E60h; Size
0x1800a85b7  lea     rcx, [rsp+0ED8h+var_E98]; void *
0x1800a85bc  call    memset_0
0x1800a85c1  call    DebugInit
0x1800a85c6  test    rdi, rdi
0x1800a85c9  jz      loc_1800A8745
0x1800a85cf  cmp     qword ptr [rdi+20h], 0
0x1800a85d4  jz      loc_1800A8745
0x1800a85da  cmp     ebx, 80h
0x1800a85e0  jz      loc_1800A86F0
0x1800a85e6  cmp     ebx, 102h
0x1800a85ec  jz      loc_1800A86F0
0x1800a85f2  mov     ecx, [rdi]
0x1800a85f4  lea     rdx, [rsp+0ED8h+var_E98]
0x1800a85f9  mov     rax, cs:g_pRasGetNotificationEntry
0x1800a8600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8605  test    eax, eax
0x1800a8607  jz      short loc_1800A8649
0x1800a8609  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a8610  cmp     rcx, r14
0x1800a8613  jz      loc_1800A8717
0x1800a8619  test    [rcx+1Ch], ebp
0x1800a861c  jz      loc_1800A8717
0x1800a8622  cmp     byte ptr [rcx+19h], 2
0x1800a8626  jb      loc_1800A8717
0x1800a862c  mov     r9d, [rdi]
0x1800a862f  mov     edx, 5Ch ; '\'
0x1800a8634  mov     rcx, [rcx+10h]
0x1800a8638  mov     r8, r15
0x1800a863b  mov     dword ptr [rsp+0ED8h+var_EB8], eax
0x1800a863f  call    WPP_SF_Dd
0x1800a8644  jmp     loc_1800A8717
0x1800a8649  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a8650  cmp     rcx, r14
0x1800a8653  jz      short loc_1800A868E
0x1800a8655  test    [rcx+1Ch], ebp
0x1800a8658  jz      short loc_1800A868E
0x1800a865a  cmp     byte ptr [rcx+19h], 5
0x1800a865e  jb      short loc_1800A868E
0x1800a8660  mov     eax, [rdi]
0x1800a8662  mov     r9d, [rsp+0ED8h+var_E98]
0x1800a8667  mov     rcx, [rcx+10h]
0x1800a866b  mov     [rsp+0ED8h+var_EA8], eax
0x1800a866f  lea     rax, [rsp+0ED8h+var_D68]
0x1800a8677  mov     [rsp+0ED8h+var_EB0], rax
0x1800a867c  lea     rax, [rsp+0ED8h+var_B66]
0x1800a8684  mov     [rsp+0ED8h+var_EB8], rax
0x1800a8689  call    WPP_SF_lSSD
0x1800a868e  lea     rcx, [rsp+0ED8h+StackSizeInBytes]; StackSizeInBytes
0x1800a8696  call    cs:__imp_SetThreadStackGuarantee
0x1800a869c  test    eax, eax
0x1800a869e  jnz     short loc_1800A86D4
0x1800a86a0  mov     rbx, cs:WPP_GLOBAL_Control
0x1800a86a7  cmp     rbx, r14
0x1800a86aa  jz      short loc_1800A86D4
0x1800a86ac  test    [rbx+1Ch], ebp
0x1800a86af  jz      short loc_1800A86D4
0x1800a86b1  cmp     byte ptr [rbx+19h], 3
0x1800a86b5  jb      short loc_1800A86D4
0x1800a86b7  mov     rbx, [rbx+10h]
0x1800a86bb  call    cs:__imp_GetLastError
0x1800a86c1  mov     edx, 5Eh ; '^'
0x1800a86c6  mov     r8, r15
0x1800a86c9  mov     r9d, eax
0x1800a86cc  mov     rcx, rbx
0x1800a86cf  call    WPP_SF_d
0x1800a86d4  mov     rdx, [rdi+20h]
0x1800a86d8  lea     r8, [rsp+0ED8h+var_E98]
0x1800a86dd  mov     rax, [rdi+18h]
0x1800a86e1  mov     r9d, 1
0x1800a86e7  xor     ecx, ecx
0x1800a86e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a86ee  jmp     short loc_1800A8717
0x1800a86f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a86f7  cmp     rcx, r14
0x1800a86fa  jz      short loc_1800A8717
0x1800a86fc  test    [rcx+1Ch], ebp
0x1800a86ff  jz      short loc_1800A8717
0x1800a8701  cmp     byte ptr [rcx+19h], 2
0x1800a8705  jb      short loc_1800A8717
0x1800a8707  mov     r9d, [rdi]
0x1800a870a  mov     rcx, [rcx+10h]
0x1800a870e  mov     dword ptr [rsp+0ED8h+var_EB8], ebx
0x1800a8712  call    WPP_SF_Dl
0x1800a8717  mov     rdx, [rdi+8]; h
0x1800a871b  xor     r8d, r8d; pftTimeout
0x1800a871e  mov     rcx, rsi; pwa
0x1800a8721  call    cs:__imp_SetThreadpoolWait
0x1800a8727  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a872e  cmp     rcx, r14
0x1800a8731  jz      short loc_1800A8795
0x1800a8733  test    [rcx+1Ch], ebp
0x1800a8736  jz      short loc_1800A8795
0x1800a8738  cmp     byte ptr [rcx+19h], 6
0x1800a873c  jb      short loc_1800A8795
0x1800a873e  mov     edx, 5Fh ; '_'
0x1800a8743  jmp     short loc_1800A8789
0x1800a8745  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a874c  cmp     rcx, r14
0x1800a874f  jz      short loc_1800A8795
0x1800a8751  test    [rcx+1Ch], ebp
0x1800a8754  jz      short loc_1800A8774
0x1800a8756  cmp     byte ptr [rcx+19h], 2
0x1800a875a  jb      short loc_1800A8774
0x1800a875c  mov     rcx, [rcx+10h]
0x1800a8760  mov     edx, 59h ; 'Y'
0x1800a8765  mov     r8, r15
0x1800a8768  call    WPP_SF_
0x1800a876d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a8774  cmp     rcx, r14
0x1800a8777  jz      short loc_1800A8795
0x1800a8779  test    [rcx+1Ch], ebp
0x1800a877c  jz      short loc_1800A8795
0x1800a877e  cmp     byte ptr [rcx+19h], 6
0x1800a8782  jb      short loc_1800A8795
0x1800a8784  mov     edx, 5Ah ; 'Z'
0x1800a8789  mov     rcx, [rcx+10h]
0x1800a878d  mov     r8, r15
0x1800a8790  call    WPP_SF_
0x1800a8795  add     rsp, 0EA8h
0x1800a879c  pop     r15
0x1800a879e  pop     r14
0x1800a87a0  pop     rdi
0x1800a87a1  pop     rsi
0x1800a87a2  pop     rbp
0x1800a87a3  pop     rbx
0x1800a87a4  retn
```
