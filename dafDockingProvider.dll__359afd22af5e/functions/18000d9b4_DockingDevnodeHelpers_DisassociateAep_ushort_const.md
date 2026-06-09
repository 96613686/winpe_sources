# DockingDevnodeHelpers::DisassociateAep(ushort const *)

- ea: `0x18000d9b4`
- end: `0x18000dcc8`
- name: `?DisassociateAep@DockingDevnodeHelpers@@SAJPEBG@Z`
- size: `788`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x18000f3ec`
- `0x180018be0`
- `0x18001c1d0`

## callees

- `0x18000d9b4`
- `0x18000f9ec`
- `0x18000ff04`
- `0x180010010`
- `0x1800101d8`
- `0x180010254`
- `0x18001ca3e`
- `0x18001ca4a`
- `0x18001ca70`

## import_xrefs

- `deviceassociation!DafStartRemoveAssociation` at `0x18000db7f`
- `deviceassociation!DafStartRemoveAssociation` at `0x18000db7f`
- `deviceassociation!DafCreateAssociationContext` at `0x18000daff`
- `deviceassociation!DafCreateAssociationContext` at `0x18000daff`
- `deviceassociation!DafCloseAssociationContext` at `0x18000db51`
- `deviceassociation!DafCloseAssociationContext` at `0x18000dbc5`
- `deviceassociation!DafCloseAssociationContext` at `0x18000dc73`
- `deviceassociation!DafCloseAssociationContext` at `0x18000db51`
- `deviceassociation!DafCloseAssociationContext` at `0x18000dbc5`
- `deviceassociation!DafCloseAssociationContext` at `0x18000dc73`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000da91`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000da91`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000dbea`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000dbea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dab1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dbf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dab1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dbf4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000db46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dbba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dc68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000db46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dbba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dc68`

## pseudocode

```c
__int64 __fastcall DockingDevnodeHelpers::DisassociateAep(unsigned __int16 *a1)
{
  int v2; // eax
  int v3; // edx
  int v4; // r8d
  unsigned int v5; // edi
  signed int LastError; // eax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  int v10; // eax
  int v11; // eax
  _QWORD *v12; // rcx
  bool v13; // zf
  int v14; // eax
  int v15; // edx
  __int64 v16; // r8
  signed int v17; // eax
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-C8h]
  unsigned int v21; // [rsp+40h] [rbp-C0h]
  unsigned __int16 v22[8]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t v23; // [rsp+60h] [rbp-A0h]
  _BYTE v24[574]; // [rsp+62h] [rbp-9Eh] BYREF

  v23 = aDocking[8];
  *(_OWORD *)v22 = *(_OWORD *)L"Docking#";
  memset_0(v24, 0, 0x238u);
  if ( wcsncmp_0(L"Docking#", a1, 8u) )
  {
    v2 = StringCbCatW(v22, 0x24Au, a1);
    v5 = v2;
    if ( v2 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_SSd(*((_QWORD *)WPP_GLOBAL_Control + 2), v3, v4, (unsigned int)v22, (__int64)a1, v2);
      }
      return v5;
    }
    a1 = v22;
  }
  hObject = CreateEventW(0, 0, 0, 0);
  if ( hObject )
  {
    v10 = DafCreateAssociationContext(a1, 0, 0, 0, &v19);
    v21 = v10;
    v5 = v10;
    if ( v10 < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 38;
        v9 = (unsigned int)v10;
        goto LABEL_20;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v21 = v5;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 37;
      v9 = v5;
LABEL_20:
      WPP_SF_d(v7[2], v8, &WPP_1e392510015231dbb7e523a39e1e58fb_Traceguids, v9);
      v5 = v21;
    }
  }
  if ( (v5 & 0x80000000) != 0 )
  {
    CloseHandle(hObject);
    v11 = DafCloseAssociationContext(v19);
    if ( v11 >= 0 )
      return v5;
    v12 = WPP_GLOBAL_Control;
    v13 = WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control;
    goto LABEL_46;
  }
  v14 = DafStartRemoveAssociation(v19, DisassociationContext::DisassociatAepCallback, &v19);
  v5 = v14;
  if ( v14 >= 0 )
  {
    if ( WaitForSingleObject(hObject, 0xFFFFFFFF) )
    {
      v17 = GetLastError();
      v5 = v17;
      if ( v17 > 0 )
        v5 = (unsigned __int16)v17 | 0x80070000;
    }
    else
    {
      v5 = v21;
    }
    if ( (v5 & 0x80000000) == 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, v16, a1);
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && *((_BYTE *)WPP_GLOBAL_Control + 25)
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, v16, (_DWORD)a1, v5);
    }
    CloseHandle(hObject);
    v11 = DafCloseAssociationContext(v19);
    if ( v11 < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      v13 = WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control;
      goto LABEL_46;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        &WPP_1e392510015231dbb7e523a39e1e58fb_Traceguids,
        (unsigned int)v14);
    }
    CloseHandle(hObject);
    v11 = DafCloseAssociationContext(v19);
    if ( v11 < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      v13 = WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control;
LABEL_46:
      if ( !v13 && *((_BYTE *)v12 + 25) && (*((_BYTE *)v12 + 28) & 1) != 0 )
        WPP_SF_d(v12[2], 39, &WPP_1e392510015231dbb7e523a39e1e58fb_Traceguids, (unsigned int)v11);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18000d9b4  push    rbp
0x18000d9b6  push    rbx
0x18000d9b7  push    rsi
0x18000d9b8  push    rdi
0x18000d9b9  push    r14
0x18000d9bb  push    r15
0x18000d9bd  lea     rbp, [rsp-1B8h]
0x18000d9c5  sub     rsp, 2B8h
0x18000d9cc  mov     rax, cs:__security_cookie
0x18000d9d3  xor     rax, rsp
0x18000d9d6  mov     [rbp+1E0h+var_40], rax
0x18000d9dd  movups  xmm0, xmmword ptr cs:aDocking; "Docking#"
0x18000d9e4  movzx   eax, word ptr cs:aDocking+10h; ""
0x18000d9eb  mov     r14, rcx
0x18000d9ee  xor     edx, edx; Val
0x18000d9f0  mov     [rsp+2E0h+var_280], ax
0x18000d9f5  mov     r8d, 238h; Size
0x18000d9fb  movaps  xmmword ptr [rsp+2E0h+var_290], xmm0
0x18000da00  lea     rcx, [rsp+2E0h+var_27E]; void *
0x18000da05  call    memset_0
0x18000da0a  mov     r8d, 8; MaxCount
0x18000da10  lea     rcx, aDocking; "Docking#"
0x18000da17  mov     rdx, r14; String2
0x18000da1a  call    wcsncmp_0
0x18000da1f  test    eax, eax
0x18000da21  jz      short loc_18000DA87
0x18000da23  mov     r8, r14; unsigned __int16 *
0x18000da26  lea     rcx, [rsp+2E0h+var_290]; unsigned __int16 *
0x18000da2b  mov     edx, 24Ah; unsigned __int64
0x18000da30  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x18000da35  mov     edi, eax
0x18000da37  test    eax, eax
0x18000da39  jns     short loc_18000DA82
0x18000da3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da42  lea     rsi, WPP_GLOBAL_Control
0x18000da49  cmp     rcx, rsi
0x18000da4c  jz      loc_18000DCA7
0x18000da52  mov     bl, 1
0x18000da54  cmp     [rcx+19h], bl
0x18000da57  jb      loc_18000DCA7
0x18000da5d  test    [rcx+1Ch], bl
0x18000da60  jz      loc_18000DCA7
0x18000da66  mov     rcx, [rcx+10h]
0x18000da6a  lea     r9, [rsp+2E0h+var_290]
0x18000da6f  mov     [rsp+2E0h+var_2B8], eax
0x18000da73  mov     [rsp+2E0h+var_2C0], r14
0x18000da78  call    WPP_SF_SSd
0x18000da7d  jmp     loc_18000DCA7
0x18000da82  lea     r14, [rsp+2E0h+var_290]
0x18000da87  xor     r9d, r9d; lpName
0x18000da8a  xor     r8d, r8d; bInitialState
0x18000da8d  xor     edx, edx; bManualReset
0x18000da8f  xor     ecx, ecx; lpEventAttributes
0x18000da91  call    cs:__imp_CreateEventW
0x18000da97  mov     [rsp+2E0h+hObject], rax
0x18000da9c  lea     r15, WPP_1e392510015231dbb7e523a39e1e58fb_Traceguids
0x18000daa3  mov     bl, 1
0x18000daa5  lea     rsi, WPP_GLOBAL_Control
0x18000daac  test    rax, rax
0x18000daaf  jnz     short loc_18000DAEA
0x18000dab1  call    cs:__imp_GetLastError
0x18000dab7  mov     edi, eax
0x18000dab9  test    eax, eax
0x18000dabb  jle     short loc_18000DAC6
0x18000dabd  movzx   edi, ax
0x18000dac0  or      edi, 80070000h
0x18000dac6  mov     [rsp+2E0h+var_2A0], edi
0x18000daca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dad1  cmp     rcx, rsi
0x18000dad4  jz      short loc_18000DB3D
0x18000dad6  cmp     [rcx+19h], bl
0x18000dad9  jb      short loc_18000DB3D
0x18000dadb  test    [rcx+1Ch], bl
0x18000dade  jz      short loc_18000DB3D
0x18000dae0  mov     edx, 25h ; '%'
0x18000dae5  mov     r9d, edi
0x18000dae8  jmp     short loc_18000DB2D
0x18000daea  lea     rax, [rsp+2E0h+var_2B0]
0x18000daef  xor     r9d, r9d
0x18000daf2  xor     r8d, r8d
0x18000daf5  mov     [rsp+2E0h+var_2C0], rax
0x18000dafa  xor     edx, edx
0x18000dafc  mov     rcx, r14
0x18000daff  call    cs:__imp_DafCreateAssociationContext
0x18000db05  mov     [rsp+2E0h+var_2A0], eax
0x18000db09  mov     edi, eax
0x18000db0b  test    eax, eax
0x18000db0d  jns     short loc_18000DB3D
0x18000db0f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db16  cmp     rcx, rsi
0x18000db19  jz      short loc_18000DB3D
0x18000db1b  cmp     [rcx+19h], bl
0x18000db1e  jb      short loc_18000DB3D
0x18000db20  test    [rcx+1Ch], bl
0x18000db23  jz      short loc_18000DB3D
0x18000db25  mov     edx, 26h ; '&'
0x18000db2a  mov     r9d, eax
0x18000db2d  mov     rcx, [rcx+10h]
0x18000db31  mov     r8, r15
0x18000db34  call    WPP_SF_d
0x18000db39  mov     edi, [rsp+2E0h+var_2A0]
0x18000db3d  test    edi, edi
0x18000db3f  jns     short loc_18000DB6E
0x18000db41  mov     rcx, [rsp+2E0h+hObject]; hObject
0x18000db46  call    cs:__imp_CloseHandle
0x18000db4c  mov     rcx, [rsp+2E0h+var_2B0]
0x18000db51  call    cs:__imp_DafCloseAssociationContext
0x18000db57  test    eax, eax
0x18000db59  jns     loc_18000DCA7
0x18000db5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db66  cmp     rcx, rsi
0x18000db69  jmp     loc_18000DC87
0x18000db6e  mov     rcx, [rsp+2E0h+var_2B0]
0x18000db73  lea     r8, [rsp+2E0h+var_2B0]
0x18000db78  lea     rdx, ?DisassociatAepCallback@DisassociationContext@@SAXPEAXJ@Z; DisassociationContext::DisassociatAepCallback(void *,long)
0x18000db7f  call    cs:__imp_DafStartRemoveAssociation
0x18000db85  mov     edi, eax
0x18000db87  test    eax, eax
0x18000db89  jns     short loc_18000DBE2
0x18000db8b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db92  cmp     rcx, rsi
0x18000db95  jz      short loc_18000DBB5
0x18000db97  cmp     [rcx+19h], bl
0x18000db9a  jb      short loc_18000DBB5
0x18000db9c  test    [rcx+1Ch], bl
0x18000db9f  jz      short loc_18000DBB5
0x18000dba1  mov     rcx, [rcx+10h]
0x18000dba5  mov     edx, 2Ah ; '*'
0x18000dbaa  mov     r9d, eax
0x18000dbad  mov     r8, r15
0x18000dbb0  call    WPP_SF_d
0x18000dbb5  mov     rcx, [rsp+2E0h+hObject]; hObject
0x18000dbba  call    cs:__imp_CloseHandle
0x18000dbc0  mov     rcx, [rsp+2E0h+var_2B0]
0x18000dbc5  call    cs:__imp_DafCloseAssociationContext
0x18000dbcb  test    eax, eax
0x18000dbcd  jns     loc_18000DCA7
0x18000dbd3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dbda  cmp     rcx, rsi
0x18000dbdd  jmp     loc_18000DC87
0x18000dbe2  mov     rcx, [rsp+2E0h+hObject]; hHandle
0x18000dbe7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000dbea  call    cs:__imp_WaitForSingleObject
0x18000dbf0  test    eax, eax
0x18000dbf2  jz      short loc_18000DC0B
0x18000dbf4  call    cs:__imp_GetLastError
0x18000dbfa  mov     edi, eax
0x18000dbfc  test    eax, eax
0x18000dbfe  jle     short loc_18000DC0F
0x18000dc00  movzx   edi, ax
0x18000dc03  or      edi, 80070000h
0x18000dc09  jmp     short loc_18000DC0F
0x18000dc0b  mov     edi, [rsp+2E0h+var_2A0]
0x18000dc0f  test    edi, edi
0x18000dc11  jns     short loc_18000DC3B
0x18000dc13  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc1a  cmp     rcx, rsi
0x18000dc1d  jz      short loc_18000DC63
0x18000dc1f  cmp     [rcx+19h], bl
0x18000dc22  jb      short loc_18000DC63
0x18000dc24  test    [rcx+1Ch], bl
0x18000dc27  jz      short loc_18000DC63
0x18000dc29  mov     rcx, [rcx+10h]
0x18000dc2d  mov     r9, r14
0x18000dc30  mov     dword ptr [rsp+2E0h+var_2C0], edi
0x18000dc34  call    WPP_SF_Sd
0x18000dc39  jmp     short loc_18000DC63
0x18000dc3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc42  cmp     rcx, rsi
0x18000dc45  jz      short loc_18000DC63
0x18000dc47  cmp     byte ptr [rcx+19h], 3
0x18000dc4b  jb      short loc_18000DC63
0x18000dc4d  test    [rcx+1Ch], bl
0x18000dc50  jz      short loc_18000DC63
0x18000dc52  mov     rcx, [rcx+10h]
0x18000dc56  mov     edx, 2Ch ; ','
0x18000dc5b  mov     r9, r14
0x18000dc5e  call    WPP_SF_S
0x18000dc63  mov     rcx, [rsp+2E0h+hObject]; hObject
0x18000dc68  call    cs:__imp_CloseHandle
0x18000dc6e  mov     rcx, [rsp+2E0h+var_2B0]
0x18000dc73  call    cs:__imp_DafCloseAssociationContext
0x18000dc79  test    eax, eax
0x18000dc7b  jns     short loc_18000DCA7
0x18000dc7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc84  cmp     rcx, rsi
0x18000dc87  jz      short loc_18000DCA7
0x18000dc89  cmp     [rcx+19h], bl
0x18000dc8c  jb      short loc_18000DCA7
0x18000dc8e  test    [rcx+1Ch], bl
0x18000dc91  jz      short loc_18000DCA7
0x18000dc93  mov     rcx, [rcx+10h]
0x18000dc97  mov     r9d, eax
0x18000dc9a  mov     r8, r15
0x18000dc9d  mov     edx, 27h ; '''
0x18000dca2  call    WPP_SF_d
0x18000dca7  mov     eax, edi
0x18000dca9  mov     rcx, [rbp+1E0h+var_40]
0x18000dcb0  xor     rcx, rsp; StackCookie
0x18000dcb3  call    __security_check_cookie
0x18000dcb8  add     rsp, 2B8h
0x18000dcbf  pop     r15
0x18000dcc1  pop     r14
0x18000dcc3  pop     rdi
0x18000dcc4  pop     rsi
0x18000dcc5  pop     rbx
0x18000dcc6  pop     rbp
0x18000dcc7  retn
```
