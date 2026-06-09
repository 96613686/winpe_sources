# CSimpleRegistryWatcher::StartUpdateWatcher(void)

- ea: `0x1800ec9f4`
- end: `0x1800ecd35`
- name: `?StartUpdateWatcher@CSimpleRegistryWatcher@@IEAAJXZ`
- size: `833`
- prototype: `__int64 __fastcall(CSimpleRegistryWatcher *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x18052cdc0`

## callees

- `0x1800ec8e8`
- `0x1800ec9f4`
- `0x18010215c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800ecc52`
- `KERNEL32!CloseHandle` at `0x1800ecc89`
- `KERNEL32!CloseHandle` at `0x1800eccc1`
- `KERNEL32!CloseHandle` at `0x1800eccf9`
- `KERNEL32!CloseHandle` at `0x1800ecc52`
- `KERNEL32!CloseHandle` at `0x1800ecc89`
- `KERNEL32!CloseHandle` at `0x1800eccc1`
- `KERNEL32!CloseHandle` at `0x1800eccf9`
- `KERNEL32!GetLastError` at `0x1800eca45`
- `KERNEL32!GetLastError` at `0x1800eca7b`
- `KERNEL32!GetLastError` at `0x1800ecad7`
- `KERNEL32!GetLastError` at `0x1800ecb36`
- `KERNEL32!GetLastError` at `0x1800ecb95`
- `KERNEL32!GetLastError` at `0x1800ecbfa`
- `KERNEL32!GetLastError` at `0x1800ecc30`
- `KERNEL32!GetLastError` at `0x1800eca45`
- `KERNEL32!GetLastError` at `0x1800eca7b`
- `KERNEL32!GetLastError` at `0x1800ecad7`
- `KERNEL32!GetLastError` at `0x1800ecb36`
- `KERNEL32!GetLastError` at `0x1800ecb95`
- `KERNEL32!GetLastError` at `0x1800ecbfa`
- `KERNEL32!GetLastError` at `0x1800ecc30`
- `KERNEL32!CreateEventW` at `0x1800eca18`
- `KERNEL32!CreateEventW` at `0x1800eca9f`
- `KERNEL32!CreateEventW` at `0x1800ecb01`
- `KERNEL32!CreateEventW` at `0x1800ecb60`
- `KERNEL32!CreateEventW` at `0x1800eca18`
- `KERNEL32!CreateEventW` at `0x1800eca9f`
- `KERNEL32!CreateEventW` at `0x1800ecb01`
- `KERNEL32!CreateEventW` at `0x1800ecb60`
- `KERNEL32!CreateThread` at `0x1800ecbc9`
- `KERNEL32!CreateThread` at `0x1800ecbc9`

## string_xrefs

- `0x1800ecc0e`: `Update watcher thread creation failed`
- `0x1800eca5b`: `Update event handle creation failed`

## pseudocode

```c
__int64 __fastcall CSimpleRegistryWatcher::StartUpdateWatcher(CSimpleRegistryWatcher *this)
{
  unsigned int v1; // ebx
  HANDLE EventW; // rax
  char v4; // al
  signed int v5; // eax
  HANDLE *v6; // r14
  HANDLE v7; // rax
  char LastError; // al
  int v9; // edx
  const wchar_t *v10; // r9
  HANDLE v11; // rax
  HANDLE v12; // rax
  HANDLE Thread; // rax
  signed int v14; // eax
  void *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx

  v1 = 0;
  if ( *((_QWORD *)this + 1) )
    return v1;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 2) = EventW;
  if ( EventW )
  {
    v7 = CreateEventW(0, 0, 0, 0);
    v6 = (HANDLE *)((char *)this + 24);
    *((_QWORD *)this + 3) = v7;
    if ( v7 )
    {
      v11 = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)this + 4) = v11;
      if ( v11 )
      {
        v12 = CreateEventW(0, 0, 0, 0);
        *((_QWORD *)this + 5) = v12;
        if ( v12 )
        {
          Thread = CreateThread(0, 0, CSimpleRegistryWatcher::UpdateWatcherThreadProc, this, 0, 0);
          *((_QWORD *)this + 1) = Thread;
          if ( Thread )
            return v1;
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_26;
          LastError = GetLastError();
          v9 = 16;
          v10 = L"Update watcher thread creation failed";
          goto LABEL_25;
        }
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LastError = GetLastError();
          v9 = 15;
          v10 = L"Resume event handle creation failed";
          goto LABEL_25;
        }
      }
      else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        v9 = 14;
        v10 = L"Suspend event handle creation failed";
        goto LABEL_25;
      }
    }
    else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      v9 = 13;
      v10 = L"Shutdown event handle creation failed";
LABEL_25:
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        (unsigned int)WPP_4d6757e87b913ee9b8f01e6dd23dcef1_Traceguids,
        (_DWORD)v10,
        LastError);
    }
LABEL_26:
    v14 = GetLastError();
    v1 = v14;
    if ( v14 > 0 )
      v1 = (unsigned __int16)v14 | 0x80070000;
    goto LABEL_28;
  }
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v4 = GetLastError();
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      (unsigned int)WPP_4d6757e87b913ee9b8f01e6dd23dcef1_Traceguids,
      (unsigned int)L"Update event handle creation failed",
      v4);
  }
  v5 = GetLastError();
  v1 = v5;
  if ( v5 > 0 )
    v1 = (unsigned __int16)v5 | 0x80070000;
  v6 = (HANDLE *)((char *)this + 24);
LABEL_28:
  if ( (v1 & 0x80000000) != 0 )
  {
    v15 = (void *)*((_QWORD *)this + 2);
    if ( v15
      && !CloseHandle(v15)
      && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_4d6757e87b913ee9b8f01e6dd23dcef1_Traceguids);
    }
    if ( *v6
      && !CloseHandle(*v6)
      && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_4d6757e87b913ee9b8f01e6dd23dcef1_Traceguids);
    }
    v16 = (void *)*((_QWORD *)this + 4);
    if ( v16
      && !CloseHandle(v16)
      && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_4d6757e87b913ee9b8f01e6dd23dcef1_Traceguids);
    }
    v17 = (void *)*((_QWORD *)this + 5);
    if ( v17
      && !CloseHandle(v17)
      && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_4d6757e87b913ee9b8f01e6dd23dcef1_Traceguids);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1800ec9f4  push    rbx
0x1800ec9f6  push    rbp
0x1800ec9f7  push    rsi
0x1800ec9f8  push    rdi
0x1800ec9f9  push    r14
0x1800ec9fb  sub     rsp, 30h
0x1800ec9ff  xor     ebx, ebx
0x1800eca01  mov     rbp, rcx
0x1800eca04  cmp     [rcx+8], rbx
0x1800eca08  jnz     loc_1800ECD28
0x1800eca0e  xor     r9d, r9d; lpName
0x1800eca11  xor     r8d, r8d; bInitialState
0x1800eca14  xor     edx, edx; bManualReset
0x1800eca16  xor     ecx, ecx; lpEventAttributes
0x1800eca18  call    cs:__imp_CreateEventW
0x1800eca1e  mov     [rbp+10h], rax
0x1800eca22  test    rax, rax
0x1800eca25  jnz     short loc_1800ECA95
0x1800eca27  mov     rax, cs:WPP_GLOBAL_Control
0x1800eca2e  lea     rsi, WPP_GLOBAL_Control
0x1800eca35  mov     edi, 80070000h
0x1800eca3a  cmp     rax, rsi
0x1800eca3d  jz      short loc_1800ECA7B
0x1800eca3f  cmp     byte ptr [rax+19h], 2
0x1800eca43  jb      short loc_1800ECA7B
0x1800eca45  call    cs:__imp_GetLastError
0x1800eca4b  test    eax, eax
0x1800eca4d  jle     short loc_1800ECA54
0x1800eca4f  movzx   eax, ax
0x1800eca52  or      eax, edi
0x1800eca54  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eca5b  lea     r9, aUpdateEventHan; "Update event handle creation failed"
0x1800eca62  mov     edx, 0Ch
0x1800eca67  mov     [rsp+58h+dwCreationFlags], eax
0x1800eca6b  lea     r8, WPP_4d6757e87b913ee9b8f01e6dd23dcef1_Traceguids
0x1800eca72  mov     rcx, [rcx+10h]
0x1800eca76  call    WPP_SF_Sd
0x1800eca7b  call    cs:__imp_GetLastError
0x1800eca81  mov     ebx, eax
0x1800eca83  test    eax, eax
0x1800eca85  jle     short loc_1800ECA8C
0x1800eca87  movzx   ebx, ax
0x1800eca8a  or      ebx, edi
0x1800eca8c  lea     r14, [rbp+18h]
0x1800eca90  jmp     loc_1800ECC41
0x1800eca95  xor     r9d, r9d; lpName
0x1800eca98  xor     r8d, r8d; bInitialState
0x1800eca9b  xor     edx, edx; bManualReset
0x1800eca9d  xor     ecx, ecx; lpEventAttributes
0x1800eca9f  call    cs:__imp_CreateEventW
0x1800ecaa5  lea     r14, [rbp+18h]
0x1800ecaa9  mov     [r14], rax
0x1800ecaac  test    rax, rax
0x1800ecaaf  jnz     short loc_1800ECAF7
0x1800ecab1  mov     rax, cs:WPP_GLOBAL_Control
0x1800ecab8  lea     rsi, WPP_GLOBAL_Control
0x1800ecabf  mov     edi, 80070000h
0x1800ecac4  cmp     rax, rsi
0x1800ecac7  jz      loc_1800ECC30
0x1800ecacd  cmp     byte ptr [rax+19h], 2
0x1800ecad1  jb      loc_1800ECC30
0x1800ecad7  call    cs:__imp_GetLastError
0x1800ecadd  test    eax, eax
0x1800ecadf  jle     short loc_1800ECAE6
0x1800ecae1  movzx   eax, ax
0x1800ecae4  or      eax, edi
0x1800ecae6  mov     edx, 0Dh
0x1800ecaeb  lea     r9, aShutdownEventH; "Shutdown event handle creation failed"
0x1800ecaf2  jmp     loc_1800ECC15
0x1800ecaf7  xor     r9d, r9d; lpName
0x1800ecafa  xor     r8d, r8d; bInitialState
0x1800ecafd  xor     edx, edx; bManualReset
0x1800ecaff  xor     ecx, ecx; lpEventAttributes
0x1800ecb01  call    cs:__imp_CreateEventW
0x1800ecb07  mov     [rbp+20h], rax
0x1800ecb0b  test    rax, rax
0x1800ecb0e  jnz     short loc_1800ECB56
0x1800ecb10  mov     rax, cs:WPP_GLOBAL_Control
0x1800ecb17  lea     rsi, WPP_GLOBAL_Control
0x1800ecb1e  mov     edi, 80070000h
0x1800ecb23  cmp     rax, rsi
0x1800ecb26  jz      loc_1800ECC30
0x1800ecb2c  cmp     byte ptr [rax+19h], 2
0x1800ecb30  jb      loc_1800ECC30
0x1800ecb36  call    cs:__imp_GetLastError
0x1800ecb3c  test    eax, eax
0x1800ecb3e  jle     short loc_1800ECB45
0x1800ecb40  movzx   eax, ax
0x1800ecb43  or      eax, edi
0x1800ecb45  mov     edx, 0Eh
0x1800ecb4a  lea     r9, aSuspendEventHa; "Suspend event handle creation failed"
0x1800ecb51  jmp     loc_1800ECC15
0x1800ecb56  xor     r9d, r9d; lpName
0x1800ecb59  xor     r8d, r8d; bInitialState
0x1800ecb5c  xor     edx, edx; bManualReset
0x1800ecb5e  xor     ecx, ecx; lpEventAttributes
0x1800ecb60  call    cs:__imp_CreateEventW
0x1800ecb66  mov     [rbp+28h], rax
0x1800ecb6a  test    rax, rax
0x1800ecb6d  jnz     short loc_1800ECBB2
0x1800ecb6f  mov     rax, cs:WPP_GLOBAL_Control
0x1800ecb76  lea     rsi, WPP_GLOBAL_Control
0x1800ecb7d  mov     edi, 80070000h
0x1800ecb82  cmp     rax, rsi
0x1800ecb85  jz      loc_1800ECC30
0x1800ecb8b  cmp     byte ptr [rax+19h], 2
0x1800ecb8f  jb      loc_1800ECC30
0x1800ecb95  call    cs:__imp_GetLastError
0x1800ecb9b  test    eax, eax
0x1800ecb9d  jle     short loc_1800ECBA4
0x1800ecb9f  movzx   eax, ax
0x1800ecba2  or      eax, edi
0x1800ecba4  mov     edx, 0Fh
0x1800ecba9  lea     r9, aResumeEventHan; "Resume event handle creation failed"
0x1800ecbb0  jmp     short loc_1800ECC15
0x1800ecbb2  mov     [rsp+58h+lpThreadId], rbx; lpThreadId
0x1800ecbb7  lea     r8, ?UpdateWatcherThreadProc@CSimpleRegistryWatcher@@CAKPEAX@Z; lpStartAddress
0x1800ecbbe  mov     r9, rbp; lpParameter
0x1800ecbc1  mov     [rsp+58h+dwCreationFlags], ebx; dwCreationFlags
0x1800ecbc5  xor     edx, edx; dwStackSize
0x1800ecbc7  xor     ecx, ecx; lpThreadAttributes
0x1800ecbc9  call    cs:__imp_CreateThread
0x1800ecbcf  mov     [rbp+8], rax
0x1800ecbd3  test    rax, rax
0x1800ecbd6  jnz     loc_1800ECD28
0x1800ecbdc  mov     rax, cs:WPP_GLOBAL_Control
0x1800ecbe3  lea     rsi, WPP_GLOBAL_Control
0x1800ecbea  mov     edi, 80070000h
0x1800ecbef  cmp     rax, rsi
0x1800ecbf2  jz      short loc_1800ECC30
0x1800ecbf4  cmp     byte ptr [rax+19h], 2
0x1800ecbf8  jb      short loc_1800ECC30
0x1800ecbfa  call    cs:__imp_GetLastError
0x1800ecc00  test    eax, eax
0x1800ecc02  jle     short loc_1800ECC09
0x1800ecc04  movzx   eax, ax
0x1800ecc07  or      eax, edi
0x1800ecc09  mov     edx, 10h
0x1800ecc0e  lea     r9, aUpdateWatcherT; "Update watcher thread creation failed"
0x1800ecc15  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ecc1c  lea     r8, WPP_4d6757e87b913ee9b8f01e6dd23dcef1_Traceguids
0x1800ecc23  mov     [rsp+58h+dwCreationFlags], eax
0x1800ecc27  mov     rcx, [rcx+10h]
0x1800ecc2b  call    WPP_SF_Sd
0x1800ecc30  call    cs:__imp_GetLastError
0x1800ecc36  mov     ebx, eax
0x1800ecc38  test    eax, eax
0x1800ecc3a  jle     short loc_1800ECC41
0x1800ecc3c  movzx   ebx, ax
0x1800ecc3f  or      ebx, edi
0x1800ecc41  test    ebx, ebx
0x1800ecc43  jns     loc_1800ECD28
0x1800ecc49  mov     rcx, [rbp+10h]; hObject
0x1800ecc4d  test    rcx, rcx
0x1800ecc50  jz      short loc_1800ECC81
0x1800ecc52  call    cs:__imp_CloseHandle
0x1800ecc58  test    eax, eax
0x1800ecc5a  jnz     short loc_1800ECC81
0x1800ecc5c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ecc63  cmp     rcx, rsi
0x1800ecc66  jz      short loc_1800ECC81
0x1800ecc68  cmp     byte ptr [rcx+19h], 2
0x1800ecc6c  jb      short loc_1800ECC81
0x1800ecc6e  mov     rcx, [rcx+10h]
0x1800ecc72  lea     edx, [rax+11h]
0x1800ecc75  lea     r8, WPP_4d6757e87b913ee9b8f01e6dd23dcef1_Traceguids
0x1800ecc7c  call    WPP_SF_
0x1800ecc81  mov     rcx, [r14]; hObject
0x1800ecc84  test    rcx, rcx
0x1800ecc87  jz      short loc_1800ECCB8
0x1800ecc89  call    cs:__imp_CloseHandle
0x1800ecc8f  test    eax, eax
0x1800ecc91  jnz     short loc_1800ECCB8
0x1800ecc93  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ecc9a  cmp     rcx, rsi
0x1800ecc9d  jz      short loc_1800ECCB8
0x1800ecc9f  cmp     byte ptr [rcx+19h], 2
0x1800ecca3  jb      short loc_1800ECCB8
0x1800ecca5  mov     rcx, [rcx+10h]
0x1800ecca9  lea     edx, [rax+12h]
0x1800eccac  lea     r8, WPP_4d6757e87b913ee9b8f01e6dd23dcef1_Traceguids
0x1800eccb3  call    WPP_SF_
0x1800eccb8  mov     rcx, [rbp+20h]; hObject
0x1800eccbc  test    rcx, rcx
0x1800eccbf  jz      short loc_1800ECCF0
0x1800eccc1  call    cs:__imp_CloseHandle
0x1800eccc7  test    eax, eax
0x1800eccc9  jnz     short loc_1800ECCF0
0x1800ecccb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eccd2  cmp     rcx, rsi
0x1800eccd5  jz      short loc_1800ECCF0
0x1800eccd7  cmp     byte ptr [rcx+19h], 2
0x1800eccdb  jb      short loc_1800ECCF0
0x1800eccdd  mov     rcx, [rcx+10h]
0x1800ecce1  lea     edx, [rax+13h]
0x1800ecce4  lea     r8, WPP_4d6757e87b913ee9b8f01e6dd23dcef1_Traceguids
0x1800ecceb  call    WPP_SF_
0x1800eccf0  mov     rcx, [rbp+28h]; hObject
0x1800eccf4  test    rcx, rcx
0x1800eccf7  jz      short loc_1800ECD28
0x1800eccf9  call    cs:__imp_CloseHandle
0x1800eccff  test    eax, eax
0x1800ecd01  jnz     short loc_1800ECD28
0x1800ecd03  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ecd0a  cmp     rcx, rsi
0x1800ecd0d  jz      short loc_1800ECD28
0x1800ecd0f  cmp     byte ptr [rcx+19h], 2
0x1800ecd13  jb      short loc_1800ECD28
0x1800ecd15  mov     rcx, [rcx+10h]
0x1800ecd19  lea     edx, [rax+14h]
0x1800ecd1c  lea     r8, WPP_4d6757e87b913ee9b8f01e6dd23dcef1_Traceguids
0x1800ecd23  call    WPP_SF_
0x1800ecd28  mov     eax, ebx
0x1800ecd2a  add     rsp, 30h
0x1800ecd2e  pop     r14
0x1800ecd30  pop     rdi
0x1800ecd31  pop     rsi
0x1800ecd32  pop     rbp
0x1800ecd33  pop     rbx
0x1800ecd34  retn
```
