# RasDoIke

- ea: `0x1800182f0`
- end: `0x180018569`
- name: `RasDoIke`
- size: `633`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800030d0`
- `0x180012330`
- `0x1800182f0`
- `0x180021b14`
- `0x1800225a0`
- `0x18002739e`
- `0x1800273d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180018447`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180018447`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001835a`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001835a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800184fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800184fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018375`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018375`

## pseudocode

```c
__int64 __fastcall RasDoIke(__int64 a1, __int64 a2, __int64 a3)
{
  HANDLE EventA; // rax
  void *v6; // rsi
  DWORD LastError; // eax
  DWORD v8; // ebx
  PVOID *v9; // rcx
  DWORD v10; // eax
  DWORD v11; // edi
  PVOID *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  DWORD v15; // eax
  DWORD v16; // eax
  _DWORD v18[232]; // [rsp+30h] [rbp-3D8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 643, a3, a1, a2);
  }
  EventA = CreateEventA(0, 0, 0, 0);
  v6 = EventA;
  if ( EventA )
  {
    v10 = SubmitLocalRequest(0x75u, a2, EventA);
    v11 = v10;
    if ( v10 )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 645, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v10);
          v12 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 0x40) != 0 && *((_BYTE *)v12 + 25) >= 2u )
        {
          v13 = 648;
          v14 = v11;
LABEL_36:
          WPP_SF_d(v12[2], v13, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v14);
        }
      }
    }
    else
    {
      while ( 1 )
      {
        v15 = WaitForSingleObject(v6, 0x1F4u);
        if ( v15 != 258 )
          break;
        memset_0(v18, 0, 0x398u);
        v16 = SubmitRequest(0, 0x16u, a2, v18);
        v11 = v16;
        if ( v16 )
        {
          v12 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v13 = 646;
LABEL_35:
            v14 = v16;
            goto LABEL_36;
          }
          goto LABEL_37;
        }
        if ( v18[0] == 1 || v18[1] == 1 )
          goto LABEL_37;
      }
      if ( !v15 )
      {
        v16 = SubmitLocalRequest(0x76u, a2, a3);
        v11 = v16;
        if ( v16 )
        {
          v12 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v13 = 647;
            goto LABEL_35;
          }
        }
      }
    }
LABEL_37:
    CloseHandle(v6);
    v8 = 0;
    if ( v11 != -2147467260 )
      v8 = v11;
    goto LABEL_39;
  }
  LastError = GetLastError();
  v8 = LastError;
  if ( !LastError )
  {
LABEL_39:
    v9 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_40;
  }
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v8;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 644, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, LastError);
    goto LABEL_39;
  }
LABEL_40:
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x40) != 0 && *((_BYTE *)v9 + 25) >= 6u )
    WPP_SF_d(v9[2], 649, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x1800182f0  mov     [rsp+arg_18], rbx
0x1800182f5  push    rbp
0x1800182f6  push    rsi
0x1800182f7  push    rdi
0x1800182f8  push    r12
0x1800182fa  push    r15
0x1800182fc  sub     rsp, 3E0h
0x180018303  mov     rax, cs:__security_cookie
0x18001830a  xor     rax, rsp
0x18001830d  mov     [rsp+408h+var_38], rax
0x180018315  mov     rbp, r8
0x180018318  mov     rbx, rdx
0x18001831b  mov     r9, rcx
0x18001831e  mov     rcx, cs:WPP_GLOBAL_Control
0x180018325  lea     r15, WPP_GLOBAL_Control
0x18001832c  cmp     rcx, r15
0x18001832f  jz      short loc_180018350
0x180018331  test    byte ptr [rcx+1Ch], 40h
0x180018335  jz      short loc_180018350
0x180018337  cmp     byte ptr [rcx+19h], 6
0x18001833b  jb      short loc_180018350
0x18001833d  mov     rcx, [rcx+10h]
0x180018341  mov     edx, 283h
0x180018346  mov     [rsp+408h+var_3E8], rbx
0x18001834b  call    WPP_SF_qq
0x180018350  xor     r9d, r9d; lpName
0x180018353  xor     r8d, r8d; bInitialState
0x180018356  xor     edx, edx; bManualReset
0x180018358  xor     ecx, ecx; lpEventAttributes
0x18001835a  call    cs:__imp_CreateEventA
0x180018361  nop     dword ptr [rax+rax+00h]
0x180018366  lea     r12, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001836d  mov     rsi, rax
0x180018370  test    rax, rax
0x180018373  jnz     short loc_1800183C8
0x180018375  call    cs:__imp_GetLastError
0x18001837c  nop     dword ptr [rax+rax+00h]
0x180018381  mov     ebx, eax
0x180018383  test    eax, eax
0x180018385  jz      loc_180018513
0x18001838b  mov     rcx, cs:WPP_GLOBAL_Control
0x180018392  cmp     rcx, r15
0x180018395  jz      loc_18001853F
0x18001839b  test    byte ptr [rcx+1Ch], 40h
0x18001839f  jz      loc_18001851A
0x1800183a5  cmp     byte ptr [rcx+19h], 2
0x1800183a9  jb      loc_18001851A
0x1800183af  mov     rcx, [rcx+10h]
0x1800183b3  mov     edx, 284h
0x1800183b8  mov     r9d, eax
0x1800183bb  mov     r8, r12
0x1800183be  call    WPP_SF_d
0x1800183c3  jmp     loc_180018513
0x1800183c8  mov     ecx, 75h ; 'u'
0x1800183cd  mov     r8, rsi
0x1800183d0  mov     rdx, rbx
0x1800183d3  call    SubmitLocalRequest
0x1800183d8  mov     edi, eax
0x1800183da  test    eax, eax
0x1800183dc  jz      short loc_18001843F
0x1800183de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800183e5  cmp     rcx, r15
0x1800183e8  jz      loc_1800184F9
0x1800183ee  test    byte ptr [rcx+1Ch], 40h
0x1800183f2  jz      short loc_180018415
0x1800183f4  cmp     byte ptr [rcx+19h], 2
0x1800183f8  jb      short loc_180018415
0x1800183fa  mov     rcx, [rcx+10h]
0x1800183fe  mov     edx, 285h
0x180018403  mov     r9d, eax
0x180018406  mov     r8, r12
0x180018409  call    WPP_SF_d
0x18001840e  mov     rcx, cs:WPP_GLOBAL_Control
0x180018415  cmp     rcx, r15
0x180018418  jz      loc_1800184F9
0x18001841e  test    byte ptr [rcx+1Ch], 40h
0x180018422  jz      loc_1800184F9
0x180018428  cmp     byte ptr [rcx+19h], 2
0x18001842c  jb      loc_1800184F9
0x180018432  mov     edx, 288h
0x180018437  mov     r9d, edi
0x18001843a  jmp     loc_1800184ED
0x18001843f  mov     edx, 1F4h; dwMilliseconds
0x180018444  mov     rcx, rsi; hHandle
0x180018447  call    cs:__imp_WaitForSingleObject
0x18001844e  nop     dword ptr [rax+rax+00h]
0x180018453  cmp     eax, 102h
0x180018458  jnz     short loc_1800184B5
0x18001845a  xor     edx, edx; Val
0x18001845c  lea     rcx, [rsp+408h+var_3D8]; void *
0x180018461  mov     r8d, 398h; Size
0x180018467  call    memset_0
0x18001846c  mov     edx, 16h
0x180018471  lea     r9, [rsp+408h+var_3D8]
0x180018476  mov     r8, rbx
0x180018479  xor     ecx, ecx
0x18001847b  call    SubmitRequest
0x180018480  mov     edi, eax
0x180018482  test    eax, eax
0x180018484  jnz     short loc_180018496
0x180018486  cmp     [rsp+408h+var_3D8], 1
0x18001848b  jz      short loc_1800184F9
0x18001848d  cmp     [rsp+408h+var_3D4], 1
0x180018492  jnz     short loc_18001843F
0x180018494  jmp     short loc_1800184F9
0x180018496  mov     rcx, cs:WPP_GLOBAL_Control
0x18001849d  cmp     rcx, r15
0x1800184a0  jz      short loc_1800184F9
0x1800184a2  test    byte ptr [rcx+1Ch], 40h
0x1800184a6  jz      short loc_1800184F9
0x1800184a8  cmp     byte ptr [rcx+19h], 2
0x1800184ac  jb      short loc_1800184F9
0x1800184ae  mov     edx, 286h
0x1800184b3  jmp     short loc_1800184EA
0x1800184b5  test    eax, eax
0x1800184b7  jnz     short loc_1800184F9
0x1800184b9  lea     ecx, [rax+76h]
0x1800184bc  mov     r8, rbp
0x1800184bf  mov     rdx, rbx
0x1800184c2  call    SubmitLocalRequest
0x1800184c7  mov     edi, eax
0x1800184c9  test    eax, eax
0x1800184cb  jz      short loc_1800184F9
0x1800184cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800184d4  cmp     rcx, r15
0x1800184d7  jz      short loc_1800184F9
0x1800184d9  test    byte ptr [rcx+1Ch], 40h
0x1800184dd  jz      short loc_1800184F9
0x1800184df  cmp     byte ptr [rcx+19h], 2
0x1800184e3  jb      short loc_1800184F9
0x1800184e5  mov     edx, 287h
0x1800184ea  mov     r9d, eax
0x1800184ed  mov     rcx, [rcx+10h]
0x1800184f1  mov     r8, r12
0x1800184f4  call    WPP_SF_d
0x1800184f9  mov     rcx, rsi; hObject
0x1800184fc  call    cs:__imp_CloseHandle
0x180018503  nop     dword ptr [rax+rax+00h]
0x180018508  xor     ebx, ebx
0x18001850a  cmp     edi, 80004004h
0x180018510  cmovnz  ebx, edi
0x180018513  mov     rcx, cs:WPP_GLOBAL_Control
0x18001851a  cmp     rcx, r15
0x18001851d  jz      short loc_18001853F
0x18001851f  test    byte ptr [rcx+1Ch], 40h
0x180018523  jz      short loc_18001853F
0x180018525  cmp     byte ptr [rcx+19h], 6
0x180018529  jb      short loc_18001853F
0x18001852b  mov     rcx, [rcx+10h]
0x18001852f  mov     edx, 289h
0x180018534  mov     r9d, ebx
0x180018537  mov     r8, r12
0x18001853a  call    WPP_SF_d
0x18001853f  mov     eax, ebx
0x180018541  mov     rcx, [rsp+408h+var_38]
0x180018549  xor     rcx, rsp; StackCookie
0x18001854c  call    __security_check_cookie
0x180018551  mov     rbx, [rsp+408h+arg_18]
0x180018559  add     rsp, 3E0h
0x180018560  pop     r15
0x180018562  pop     r12
0x180018564  pop     rdi
0x180018565  pop     rsi
0x180018566  pop     rbp
0x180018567  retn
```
