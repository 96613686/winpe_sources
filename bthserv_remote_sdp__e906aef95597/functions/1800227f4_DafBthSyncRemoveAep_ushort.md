# DafBthSyncRemoveAep(ushort *)

- ea: `0x1800227f4`
- end: `0x1800229db`
- name: `?DafBthSyncRemoveAep@@YAJPEAG@Z`
- size: `487`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180022a74`

## callees

- `0x1800227f4`
- `0x18002354c`
- `0x180023628`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180022937`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180022937`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002284a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002284a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022860`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022860`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002297d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002297d`
- `deviceassociation!DafCloseAssociationContext` at `0x180022957`
- `deviceassociation!DafCloseAssociationContext` at `0x180022957`
- `deviceassociation!DafStartRemoveAssociation` at `0x180022904`
- `deviceassociation!DafStartRemoveAssociation` at `0x180022904`
- `deviceassociation!DafCreateAssociationContext` at `0x1800228c4`
- `deviceassociation!DafCreateAssociationContext` at `0x1800228c4`

## pseudocode

```c
__int64 __fastcall DafBthSyncRemoveAep(unsigned __int16 *a1)
{
  signed int LastError; // eax
  __int64 v3; // rdx
  __int64 v4; // r8
  int v5; // r9d
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  int v8; // eax
  int v9; // edx
  int v10; // eax
  bool v11; // cf
  __int64 v13; // [rsp+48h] [rbp+10h] BYREF
  HANDLE hHandle; // [rsp+50h] [rbp+18h] BYREF

  v13 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids);
  hHandle = CreateEventW(0, 1, 0, 0);
  if ( hHandle )
  {
    v8 = DafCreateAssociationContext(a1, 0, 0, 0, &v13);
    v6 = v8;
    if ( v8 >= 0 )
    {
      v8 = DafStartRemoveAssociation(v13, DafBthSyncRemoveAepComplete, &hHandle);
      v6 = v8;
      if ( v8 >= 0 )
      {
        WaitForSingleObject(hHandle, 0xFFFFFFFF);
        goto LABEL_21;
      }
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_22;
      v9 = 42;
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_22;
      v9 = 41;
    }
    WPP_SF_sd(v7[2], v9, (unsigned int)WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids, v5, v8);
LABEL_21:
    v7 = WPP_GLOBAL_Control;
    goto LABEL_22;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      40,
      (unsigned int)WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids,
      v5,
      v6);
    goto LABEL_21;
  }
LABEL_22:
  if ( v13 )
  {
    DafCloseAssociationContext(v13, v3, v4);
    v13 = 0;
    v7 = WPP_GLOBAL_Control;
  }
  if ( hHandle )
  {
    CloseHandle(hHandle);
    hHandle = 0;
    v7 = WPP_GLOBAL_Control;
  }
  v10 = 0;
  if ( v6 )
    v11 = *((_BYTE *)v7 + 25) < 2u;
  else
    v11 = *((_BYTE *)v7 + 25) < 5u;
  if ( v7 != &WPP_GLOBAL_Control )
  {
    LOBYTE(v10) = !v11;
    if ( v10 )
      WPP_SF_sd(v7[2], 43, (unsigned int)WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids, v5, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x1800227f4  mov     [rsp+arg_0], rbx
0x1800227f9  mov     [rsp+arg_18], rsi
0x1800227fe  push    r14
0x180022800  sub     rsp, 30h
0x180022804  and     [rsp+38h+arg_8], 0
0x18002280a  mov     rbx, rcx
0x18002280d  mov     rcx, cs:WPP_GLOBAL_Control
0x180022814  lea     rsi, WPP_GLOBAL_Control
0x18002281b  lea     r14, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids
0x180022822  cmp     rcx, rsi
0x180022825  jz      short loc_18002283E
0x180022827  cmp     byte ptr [rcx+19h], 5
0x18002282b  jb      short loc_18002283E
0x18002282d  mov     rcx, [rcx+10h]
0x180022831  mov     edx, 27h ; '''
0x180022836  mov     r8, r14
0x180022839  call    WPP_SF_s
0x18002283e  xor     r9d, r9d; lpName
0x180022841  xor     r8d, r8d; bInitialState
0x180022844  xor     ecx, ecx; lpEventAttributes
0x180022846  lea     edx, [r9+1]; bManualReset
0x18002284a  call    cs:__imp_CreateEventW
0x180022851  nop     dword ptr [rax+rax+00h]
0x180022856  mov     [rsp+38h+hHandle], rax
0x18002285b  test    rax, rax
0x18002285e  jnz     short loc_1800228AF
0x180022860  call    cs:__imp_GetLastError
0x180022867  nop     dword ptr [rax+rax+00h]
0x18002286c  mov     ebx, eax
0x18002286e  test    eax, eax
0x180022870  jle     short loc_18002287B
0x180022872  movzx   ebx, ax
0x180022875  or      ebx, 80070000h
0x18002287b  mov     rcx, cs:WPP_GLOBAL_Control
0x180022882  cmp     rcx, rsi
0x180022885  jz      loc_18002294A
0x18002288b  cmp     byte ptr [rcx+19h], 2
0x18002288f  jb      loc_18002294A
0x180022895  mov     edx, 28h ; '('
0x18002289a  mov     dword ptr [rsp+38h+var_18], ebx
0x18002289e  mov     rcx, [rcx+10h]
0x1800228a2  mov     r8, r14
0x1800228a5  call    WPP_SF_sd
0x1800228aa  jmp     loc_180022943
0x1800228af  lea     rax, [rsp+38h+arg_8]
0x1800228b4  xor     r9d, r9d
0x1800228b7  xor     r8d, r8d
0x1800228ba  mov     [rsp+38h+var_18], rax
0x1800228bf  xor     edx, edx
0x1800228c1  mov     rcx, rbx
0x1800228c4  call    cs:__imp_DafCreateAssociationContext
0x1800228cb  nop     dword ptr [rax+rax+00h]
0x1800228d0  mov     ebx, eax
0x1800228d2  test    eax, eax
0x1800228d4  jns     short loc_1800228F3
0x1800228d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800228dd  cmp     rcx, rsi
0x1800228e0  jz      short loc_18002294A
0x1800228e2  cmp     byte ptr [rcx+19h], 2
0x1800228e6  jb      short loc_18002294A
0x1800228e8  mov     edx, 29h ; ')'
0x1800228ed  mov     dword ptr [rsp+38h+var_18], eax
0x1800228f1  jmp     short loc_18002289E
0x1800228f3  mov     rcx, [rsp+38h+arg_8]
0x1800228f8  lea     r8, [rsp+38h+hHandle]
0x1800228fd  lea     rdx, ?DafBthSyncRemoveAepComplete@@YAXPEAXJ@Z; DafBthSyncRemoveAepComplete(void *,long)
0x180022904  call    cs:__imp_DafStartRemoveAssociation
0x18002290b  nop     dword ptr [rax+rax+00h]
0x180022910  mov     ebx, eax
0x180022912  test    eax, eax
0x180022914  jns     short loc_18002292F
0x180022916  mov     rcx, cs:WPP_GLOBAL_Control
0x18002291d  cmp     rcx, rsi
0x180022920  jz      short loc_18002294A
0x180022922  cmp     byte ptr [rcx+19h], 2
0x180022926  jb      short loc_18002294A
0x180022928  mov     edx, 2Ah ; '*'
0x18002292d  jmp     short loc_1800228ED
0x18002292f  mov     rcx, [rsp+38h+hHandle]; hHandle
0x180022934  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180022937  call    cs:__imp_WaitForSingleObject
0x18002293e  nop     dword ptr [rax+rax+00h]
0x180022943  mov     rcx, cs:WPP_GLOBAL_Control
0x18002294a  mov     rax, [rsp+38h+arg_8]
0x18002294f  test    rax, rax
0x180022952  jz      short loc_180022970
0x180022954  mov     rcx, rax
0x180022957  call    cs:__imp_DafCloseAssociationContext
0x18002295e  nop     dword ptr [rax+rax+00h]
0x180022963  and     [rsp+38h+arg_8], 0
0x180022969  mov     rcx, cs:WPP_GLOBAL_Control
0x180022970  mov     rax, [rsp+38h+hHandle]
0x180022975  test    rax, rax
0x180022978  jz      short loc_180022996
0x18002297a  mov     rcx, rax; hObject
0x18002297d  call    cs:__imp_CloseHandle
0x180022984  nop     dword ptr [rax+rax+00h]
0x180022989  and     [rsp+38h+hHandle], 0
0x18002298f  mov     rcx, cs:WPP_GLOBAL_Control
0x180022996  xor     eax, eax
0x180022998  test    ebx, ebx
0x18002299a  jnz     short loc_1800229A2
0x18002299c  cmp     byte ptr [rcx+19h], 5
0x1800229a0  jmp     short loc_1800229A6
0x1800229a2  cmp     byte ptr [rcx+19h], 2
0x1800229a6  setnb   al
0x1800229a9  cmp     rcx, rsi
0x1800229ac  jz      short loc_1800229C7
0x1800229ae  test    eax, eax
0x1800229b0  jz      short loc_1800229C7
0x1800229b2  mov     rcx, [rcx+10h]
0x1800229b6  mov     edx, 2Bh ; '+'
0x1800229bb  mov     r8, r14
0x1800229be  mov     dword ptr [rsp+38h+var_18], ebx
0x1800229c2  call    WPP_SF_sd
0x1800229c7  mov     rsi, [rsp+38h+arg_18]
0x1800229cc  mov     eax, ebx
0x1800229ce  mov     rbx, [rsp+38h+arg_0]
0x1800229d3  add     rsp, 30h
0x1800229d7  pop     r14
0x1800229d9  retn
```
