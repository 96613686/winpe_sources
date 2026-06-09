# RasProtocolUpdateConnection

- ea: `0x18001d500`
- end: `0x18001d6d1`
- name: `RasProtocolUpdateConnection`
- size: `465`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002a50`
- `0x180002f80`
- `0x18001d500`
- `0x180020fd8`
- `0x180021000`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001d617`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001d617`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001d572`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001d572`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d689`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d689`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d580`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d580`

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
0x18001d500  mov     [rsp+arg_0], rbx
0x18001d505  mov     [rsp+arg_8], rsi
0x18001d50a  push    rdi
0x18001d50b  push    r12
0x18001d50d  push    r15
0x18001d50f  sub     rsp, 30h
0x18001d513  mov     rbx, rdx
0x18001d516  mov     rsi, rcx
0x18001d519  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d520  lea     r15, WPP_GLOBAL_Control
0x18001d527  lea     r12, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d52e  cmp     rcx, r15
0x18001d531  jz      short loc_18001D550
0x18001d533  test    byte ptr [rcx+1Ch], 40h
0x18001d537  jz      short loc_18001D550
0x18001d539  cmp     byte ptr [rcx+19h], 6
0x18001d53d  jb      short loc_18001D550
0x18001d53f  mov     rcx, [rcx+10h]
0x18001d543  mov     edx, 197h
0x18001d548  mov     r8, r12
0x18001d54b  call    WPP_SF_
0x18001d550  xor     r9d, r9d; lpName
0x18001d553  mov     [rsp+48h+arg_18], 0
0x18001d55b  xor     r8d, r8d; bInitialState
0x18001d55e  mov     [rsp+48h+arg_10], 0
0x18001d566  xor     edx, edx; bManualReset
0x18001d568  mov     dword ptr [rsp+48h+var_28], 4
0x18001d570  xor     ecx, ecx; lpEventAttributes
0x18001d572  call    cs:__imp_CreateEventA
0x18001d578  mov     rdi, rax
0x18001d57b  test    rax, rax
0x18001d57e  jnz     short loc_18001D5CD
0x18001d580  call    cs:__imp_GetLastError
0x18001d586  mov     ebx, eax
0x18001d588  test    eax, eax
0x18001d58a  jz      loc_18001D68F
0x18001d590  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d597  cmp     rcx, r15
0x18001d59a  jz      loc_18001D6BB
0x18001d5a0  test    byte ptr [rcx+1Ch], 40h
0x18001d5a4  jz      loc_18001D696
0x18001d5aa  cmp     byte ptr [rcx+19h], 2
0x18001d5ae  jb      loc_18001D696
0x18001d5b4  mov     rcx, [rcx+10h]
0x18001d5b8  mov     edx, 198h
0x18001d5bd  mov     r9d, eax
0x18001d5c0  mov     r8, r12
0x18001d5c3  call    WPP_SF_d
0x18001d5c8  jmp     loc_18001D68F
0x18001d5cd  lea     r9, [rsp+48h+var_28]
0x18001d5d2  mov     edx, 0Ch
0x18001d5d7  lea     r8, [rsp+48h+arg_10]
0x18001d5dc  mov     rcx, rsi
0x18001d5df  call    RasGetConnectionUserData
0x18001d5e4  cmp     [rsp+48h+arg_10], 0
0x18001d5e9  jnz     short loc_18001D5F3
0x18001d5eb  mov     [rsp+48h+arg_10], 1Eh
0x18001d5f3  mov     ecx, 89h
0x18001d5f8  mov     r9, rbx
0x18001d5fb  mov     r8, rdi
0x18001d5fe  mov     rdx, rsi
0x18001d601  call    SubmitLocalRequest
0x18001d606  mov     ebx, eax
0x18001d608  test    eax, eax
0x18001d60a  jnz     short loc_18001D65A
0x18001d60c  imul    edx, [rsp+48h+arg_10], 3E8h; dwMilliseconds
0x18001d614  mov     rcx, rdi; hHandle
0x18001d617  call    cs:__imp_WaitForSingleObject
0x18001d61d  mov     ecx, 8Ah
0x18001d622  lea     r8, [rsp+48h+arg_18]
0x18001d627  mov     rdx, rsi
0x18001d62a  call    SubmitLocalRequest
0x18001d62f  mov     ebx, eax
0x18001d631  test    eax, eax
0x18001d633  jnz     short loc_18001D63B
0x18001d635  mov     ebx, [rsp+48h+arg_18]
0x18001d639  jmp     short loc_18001D686
0x18001d63b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d642  cmp     rcx, r15
0x18001d645  jz      short loc_18001D686
0x18001d647  test    byte ptr [rcx+1Ch], 40h
0x18001d64b  jz      short loc_18001D686
0x18001d64d  cmp     byte ptr [rcx+19h], 2
0x18001d651  jb      short loc_18001D686
0x18001d653  mov     edx, 199h
0x18001d658  jmp     short loc_18001D677
0x18001d65a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d661  cmp     rcx, r15
0x18001d664  jz      short loc_18001D686
0x18001d666  test    byte ptr [rcx+1Ch], 40h
0x18001d66a  jz      short loc_18001D686
0x18001d66c  cmp     byte ptr [rcx+19h], 2
0x18001d670  jb      short loc_18001D686
0x18001d672  mov     edx, 19Ah
0x18001d677  mov     rcx, [rcx+10h]
0x18001d67b  mov     r9d, eax
0x18001d67e  mov     r8, r12
0x18001d681  call    WPP_SF_d
0x18001d686  mov     rcx, rdi; hObject
0x18001d689  call    cs:__imp_CloseHandle
0x18001d68f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d696  cmp     rcx, r15
0x18001d699  jz      short loc_18001D6BB
0x18001d69b  test    byte ptr [rcx+1Ch], 40h
0x18001d69f  jz      short loc_18001D6BB
0x18001d6a1  cmp     byte ptr [rcx+19h], 6
0x18001d6a5  jb      short loc_18001D6BB
0x18001d6a7  mov     rcx, [rcx+10h]
0x18001d6ab  mov     edx, 19Bh
0x18001d6b0  mov     r9d, ebx
0x18001d6b3  mov     r8, r12
0x18001d6b6  call    WPP_SF_d
0x18001d6bb  mov     rsi, [rsp+48h+arg_8]
0x18001d6c0  mov     eax, ebx
0x18001d6c2  mov     rbx, [rsp+48h+arg_0]
0x18001d6c7  add     rsp, 30h
0x18001d6cb  pop     r15
0x18001d6cd  pop     r12
0x18001d6cf  pop     rdi
0x18001d6d0  retn
```
