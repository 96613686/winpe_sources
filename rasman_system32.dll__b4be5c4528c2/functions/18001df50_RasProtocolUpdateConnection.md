# RasProtocolUpdateConnection

- ea: `0x18001df50`
- end: `0x18001e13a`
- name: `RasProtocolUpdateConnection`
- size: `490`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002b90`
- `0x1800030d0`
- `0x18001df50`
- `0x180021ae4`
- `0x180021b14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001e073`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001e073`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001dfc2`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001dfc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e0eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e0eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dfd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dfd6`

## pseudocode

```c
__int64 __fastcall RasProtocolUpdateConnection(__int64 a1, __int64 a2)
{
  HANDLE EventA; // rdi
  DWORD LastError; // eax
  DWORD v6; // ebx
  PVOID *v7; // rcx
  DWORD v8; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v12[5]; // [rsp+20h] [rbp-28h] BYREF
  int v13; // [rsp+60h] [rbp+18h] BYREF
  DWORD v14; // [rsp+68h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 407, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
  }
  v14 = 0;
  v13 = 0;
  LODWORD(v12[0]) = 4;
  EventA = CreateEventA(0, 0, 0, 0);
  if ( EventA )
  {
    ((void (__fastcall *)(__int64, __int64, int *, __int64 *))RasGetConnectionUserData)(a1, 12, &v13, v12);
    if ( !v13 )
      v13 = 30;
    v8 = SubmitLocalRequest(0x89u, a1, EventA, a2, v12[0]);
    v6 = v8;
    if ( v8 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_25;
      }
      v10 = 410;
    }
    else
    {
      WaitForSingleObject(EventA, 1000 * v13);
      v8 = SubmitLocalRequest(0x8Au, a1, &v14);
      v6 = v8;
      if ( !v8 )
      {
        v6 = v14;
LABEL_25:
        CloseHandle(EventA);
        goto LABEL_26;
      }
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_25;
      }
      v10 = 409;
    }
    WPP_SF_d(v9[2], v10, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v8);
    goto LABEL_25;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( !LastError )
  {
LABEL_26:
    v7 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_27;
  }
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v6;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 408, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, LastError);
    goto LABEL_26;
  }
LABEL_27:
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x40) != 0 && *((_BYTE *)v7 + 25) >= 6u )
    WPP_SF_d(v7[2], 411, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18001df50  mov     [rsp+arg_0], rbx
0x18001df55  mov     [rsp+arg_8], rsi
0x18001df5a  push    rdi
0x18001df5b  push    r12
0x18001df5d  push    r15
0x18001df5f  sub     rsp, 30h
0x18001df63  mov     rbx, rdx
0x18001df66  mov     rsi, rcx
0x18001df69  mov     rcx, cs:WPP_GLOBAL_Control
0x18001df70  lea     r15, WPP_GLOBAL_Control
0x18001df77  lea     r12, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001df7e  cmp     rcx, r15
0x18001df81  jz      short loc_18001DFA0
0x18001df83  test    byte ptr [rcx+1Ch], 40h
0x18001df87  jz      short loc_18001DFA0
0x18001df89  cmp     byte ptr [rcx+19h], 6
0x18001df8d  jb      short loc_18001DFA0
0x18001df8f  mov     rcx, [rcx+10h]
0x18001df93  mov     edx, 197h
0x18001df98  mov     r8, r12
0x18001df9b  call    WPP_SF_
0x18001dfa0  xor     r9d, r9d; lpName
0x18001dfa3  mov     [rsp+48h+arg_18], 0
0x18001dfab  xor     r8d, r8d; bInitialState
0x18001dfae  mov     [rsp+48h+arg_10], 0
0x18001dfb6  xor     edx, edx; bManualReset
0x18001dfb8  mov     dword ptr [rsp+48h+var_28], 4
0x18001dfc0  xor     ecx, ecx; lpEventAttributes
0x18001dfc2  call    cs:__imp_CreateEventA
0x18001dfc9  nop     dword ptr [rax+rax+00h]
0x18001dfce  mov     rdi, rax
0x18001dfd1  test    rax, rax
0x18001dfd4  jnz     short loc_18001E029
0x18001dfd6  call    cs:__imp_GetLastError
0x18001dfdd  nop     dword ptr [rax+rax+00h]
0x18001dfe2  mov     ebx, eax
0x18001dfe4  test    eax, eax
0x18001dfe6  jz      loc_18001E0F7
0x18001dfec  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dff3  cmp     rcx, r15
0x18001dff6  jz      loc_18001E123
0x18001dffc  test    byte ptr [rcx+1Ch], 40h
0x18001e000  jz      loc_18001E0FE
0x18001e006  cmp     byte ptr [rcx+19h], 2
0x18001e00a  jb      loc_18001E0FE
0x18001e010  mov     rcx, [rcx+10h]
0x18001e014  mov     edx, 198h
0x18001e019  mov     r9d, eax
0x18001e01c  mov     r8, r12
0x18001e01f  call    WPP_SF_d
0x18001e024  jmp     loc_18001E0F7
0x18001e029  lea     r9, [rsp+48h+var_28]
0x18001e02e  mov     edx, 0Ch
0x18001e033  lea     r8, [rsp+48h+arg_10]
0x18001e038  mov     rcx, rsi
0x18001e03b  call    RasGetConnectionUserData
0x18001e040  cmp     [rsp+48h+arg_10], 0
0x18001e045  jnz     short loc_18001E04F
0x18001e047  mov     [rsp+48h+arg_10], 1Eh
0x18001e04f  mov     ecx, 89h
0x18001e054  mov     r9, rbx
0x18001e057  mov     r8, rdi
0x18001e05a  mov     rdx, rsi
0x18001e05d  call    SubmitLocalRequest
0x18001e062  mov     ebx, eax
0x18001e064  test    eax, eax
0x18001e066  jnz     short loc_18001E0BC
0x18001e068  imul    edx, [rsp+48h+arg_10], 3E8h; dwMilliseconds
0x18001e070  mov     rcx, rdi; hHandle
0x18001e073  call    cs:__imp_WaitForSingleObject
0x18001e07a  nop     dword ptr [rax+rax+00h]
0x18001e07f  mov     ecx, 8Ah
0x18001e084  lea     r8, [rsp+48h+arg_18]
0x18001e089  mov     rdx, rsi
0x18001e08c  call    SubmitLocalRequest
0x18001e091  mov     ebx, eax
0x18001e093  test    eax, eax
0x18001e095  jnz     short loc_18001E09D
0x18001e097  mov     ebx, [rsp+48h+arg_18]
0x18001e09b  jmp     short loc_18001E0E8
0x18001e09d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e0a4  cmp     rcx, r15
0x18001e0a7  jz      short loc_18001E0E8
0x18001e0a9  test    byte ptr [rcx+1Ch], 40h
0x18001e0ad  jz      short loc_18001E0E8
0x18001e0af  cmp     byte ptr [rcx+19h], 2
0x18001e0b3  jb      short loc_18001E0E8
0x18001e0b5  mov     edx, 199h
0x18001e0ba  jmp     short loc_18001E0D9
0x18001e0bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e0c3  cmp     rcx, r15
0x18001e0c6  jz      short loc_18001E0E8
0x18001e0c8  test    byte ptr [rcx+1Ch], 40h
0x18001e0cc  jz      short loc_18001E0E8
0x18001e0ce  cmp     byte ptr [rcx+19h], 2
0x18001e0d2  jb      short loc_18001E0E8
0x18001e0d4  mov     edx, 19Ah
0x18001e0d9  mov     rcx, [rcx+10h]
0x18001e0dd  mov     r9d, eax
0x18001e0e0  mov     r8, r12
0x18001e0e3  call    WPP_SF_d
0x18001e0e8  mov     rcx, rdi; hObject
0x18001e0eb  call    cs:__imp_CloseHandle
0x18001e0f2  nop     dword ptr [rax+rax+00h]
0x18001e0f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e0fe  cmp     rcx, r15
0x18001e101  jz      short loc_18001E123
0x18001e103  test    byte ptr [rcx+1Ch], 40h
0x18001e107  jz      short loc_18001E123
0x18001e109  cmp     byte ptr [rcx+19h], 6
0x18001e10d  jb      short loc_18001E123
0x18001e10f  mov     rcx, [rcx+10h]
0x18001e113  mov     edx, 19Bh
0x18001e118  mov     r9d, ebx
0x18001e11b  mov     r8, r12
0x18001e11e  call    WPP_SF_d
0x18001e123  mov     rsi, [rsp+48h+arg_8]
0x18001e128  mov     eax, ebx
0x18001e12a  mov     rbx, [rsp+48h+arg_0]
0x18001e12f  add     rsp, 30h
0x18001e133  pop     r15
0x18001e135  pop     r12
0x18001e137  pop     rdi
0x18001e138  retn
```
