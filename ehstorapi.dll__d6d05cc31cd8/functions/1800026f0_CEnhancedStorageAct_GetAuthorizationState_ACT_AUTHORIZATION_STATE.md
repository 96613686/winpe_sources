# CEnhancedStorageAct::GetAuthorizationState(_ACT_AUTHORIZATION_STATE *)

- ea: `0x1800026f0`
- end: `0x1800028e4`
- name: `?GetAuthorizationState@CEnhancedStorageAct@@UEAAJPEAU_ACT_AUTHORIZATION_STATE@@@Z`
- size: `500`
- prototype: `__int64 __fastcall(CEnhancedStorageAct *__hidden this, struct _ACT_AUTHORIZATION_STATE *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callees

- `0x1800026f0`
- `0x180003c54`
- `0x180003ce0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1800027b8`
- `KERNEL32!CreateFileW` at `0x1800027b8`
- `KERNEL32!GetLastError` at `0x1800027c7`
- `KERNEL32!GetLastError` at `0x180002844`
- `KERNEL32!GetLastError` at `0x1800027c7`
- `KERNEL32!GetLastError` at `0x180002844`
- `KERNEL32!DeviceIoControl` at `0x18000283a`
- `KERNEL32!DeviceIoControl` at `0x18000283a`
- `KERNEL32!CloseHandle` at `0x1800028cc`
- `KERNEL32!CloseHandle` at `0x1800028cc`

## pseudocode

```c
__int64 __fastcall CEnhancedStorageAct::GetAuthorizationState(
        CEnhancedStorageAct *this,
        struct _ACT_AUTHORIZATION_STATE *a2)
{
  const WCHAR *v4; // rcx
  __int64 v5; // r9
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  HANDLE FileW; // rsi
  signed int LastError; // eax
  signed int v11; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  __int16 OutBuffer; // [rsp+58h] [rbp+10h] BYREF
  DWORD BytesReturned; // [rsp+60h] [rbp+18h] BYREF

  OutBuffer = 0;
  BytesReturned = 0;
  if ( a2 )
  {
    v4 = (const WCHAR *)*((_QWORD *)this + 8);
    if ( !*((_DWORD *)v4 - 4) )
    {
      v5 = 2147549183LL;
      v6 = -2147418113;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        return v6;
      v8 = 29;
      goto LABEL_10;
    }
    FileW = CreateFileW(v4, 0x80000000, 3u, 0, 3u, 0, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        return v6;
      v8 = 30;
      v5 = v6;
LABEL_10:
      WPP_SF_d(v7[2], v8, WPP_86ea56442a363db295b8a4ba3de86fee_Traceguids, v5);
      return v6;
    }
    if ( DeviceIoControl(FileW, 0x2D1424u, 0, 0, &OutBuffer, 2u, &BytesReturned, 0) )
    {
      if ( BytesReturned == 2 )
      {
        v6 = 0;
        a2->ulState = HIBYTE(OutBuffer) != 0;
        goto LABEL_29;
      }
      v14 = 2147549183LL;
      v6 = -2147418113;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_29;
      v13 = 32;
    }
    else
    {
      v11 = GetLastError();
      v6 = v11;
      if ( v11 > 0 )
        v6 = (unsigned __int16)v11 | 0x80070000;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_29;
      v13 = 31;
      v14 = v6;
    }
    WPP_SF_d(v12[2], v13, WPP_86ea56442a363db295b8a4ba3de86fee_Traceguids, v14);
LABEL_29:
    CloseHandle(FileW);
    return v6;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_86ea56442a363db295b8a4ba3de86fee_Traceguids, "pState");
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800026f0  mov     [rsp+arg_0], rbx
0x1800026f5  mov     [rsp+arg_18], rsi
0x1800026fa  push    rdi
0x1800026fb  sub     rsp, 40h
0x1800026ff  xor     eax, eax
0x180002701  mov     rdi, rdx
0x180002704  mov     [rsp+48h+OutBuffer], ax
0x180002709  mov     [rsp+48h+BytesReturned], eax
0x18000270d  test    rdx, rdx
0x180002710  jnz     short loc_18000274F
0x180002712  mov     rcx, cs:WPP_GLOBAL_Control
0x180002719  lea     rax, WPP_GLOBAL_Control
0x180002720  cmp     rcx, rax
0x180002723  jz      short loc_180002745
0x180002725  test    byte ptr [rcx+1Ch], 2
0x180002729  jz      short loc_180002745
0x18000272b  mov     rcx, [rcx+10h]
0x18000272f  lea     edx, [rdi+1Ch]
0x180002732  lea     r9, aPstate; "pState"
0x180002739  lea     r8, WPP_86ea56442a363db295b8a4ba3de86fee_Traceguids
0x180002740  call    WPP_SF_s
0x180002745  mov     eax, 80070057h
0x18000274a  jmp     loc_1800028D4
0x18000274f  mov     rcx, [rcx+40h]; lpFileName
0x180002753  cmp     [rcx-10h], eax
0x180002756  jnz     short loc_18000279C
0x180002758  mov     r9d, 8000FFFFh
0x18000275e  mov     ebx, r9d
0x180002761  mov     rcx, cs:WPP_GLOBAL_Control
0x180002768  lea     rax, WPP_GLOBAL_Control
0x18000276f  cmp     rcx, rax
0x180002772  jz      loc_1800028D2
0x180002778  test    byte ptr [rcx+1Ch], 2
0x18000277c  jz      loc_1800028D2
0x180002782  mov     edx, 1Dh
0x180002787  mov     rcx, [rcx+10h]
0x18000278b  lea     r8, WPP_86ea56442a363db295b8a4ba3de86fee_Traceguids
0x180002792  call    WPP_SF_d
0x180002797  jmp     loc_1800028D2
0x18000279c  mov     [rsp+48h+hTemplateFile], rax; hTemplateFile
0x1800027a1  mov     r8d, 3; dwShareMode
0x1800027a7  mov     [rsp+48h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x1800027ab  xor     r9d, r9d; lpSecurityAttributes
0x1800027ae  mov     edx, 80000000h; dwDesiredAccess
0x1800027b3  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800027b8  call    cs:__imp_CreateFileW
0x1800027be  mov     rsi, rax
0x1800027c1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800027c5  jnz     short loc_180002807
0x1800027c7  call    cs:__imp_GetLastError
0x1800027cd  mov     ebx, eax
0x1800027cf  test    eax, eax
0x1800027d1  jle     short loc_1800027DC
0x1800027d3  movzx   ebx, ax
0x1800027d6  or      ebx, 80070000h
0x1800027dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800027e3  lea     rax, WPP_GLOBAL_Control
0x1800027ea  cmp     rcx, rax
0x1800027ed  jz      loc_1800028D2
0x1800027f3  test    byte ptr [rcx+1Ch], 2
0x1800027f7  jz      loc_1800028D2
0x1800027fd  mov     edx, 1Eh
0x180002802  mov     r9d, ebx
0x180002805  jmp     short loc_180002787
0x180002807  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x180002810  lea     rax, [rsp+48h+BytesReturned]
0x180002815  mov     [rsp+48h+hTemplateFile], rax; lpBytesReturned
0x18000281a  xor     r9d, r9d; nInBufferSize
0x18000281d  lea     rax, [rsp+48h+OutBuffer]
0x180002822  mov     [rsp+48h+dwFlagsAndAttributes], 2; nOutBufferSize
0x18000282a  xor     r8d, r8d; lpInBuffer
0x18000282d  mov     qword ptr [rsp+48h+dwCreationDisposition], rax; lpOutBuffer
0x180002832  mov     edx, 2D1424h; dwIoControlCode
0x180002837  mov     rcx, rsi; hDevice
0x18000283a  call    cs:__imp_DeviceIoControl
0x180002840  test    eax, eax
0x180002842  jnz     short loc_18000288C
0x180002844  call    cs:__imp_GetLastError
0x18000284a  mov     ebx, eax
0x18000284c  test    eax, eax
0x18000284e  jle     short loc_180002859
0x180002850  movzx   ebx, ax
0x180002853  or      ebx, 80070000h
0x180002859  mov     rcx, cs:WPP_GLOBAL_Control
0x180002860  lea     rax, WPP_GLOBAL_Control
0x180002867  cmp     rcx, rax
0x18000286a  jz      short loc_1800028C9
0x18000286c  test    byte ptr [rcx+1Ch], 2
0x180002870  jz      short loc_1800028C9
0x180002872  mov     edx, 1Fh
0x180002877  mov     r9d, ebx
0x18000287a  mov     rcx, [rcx+10h]
0x18000287e  lea     r8, WPP_86ea56442a363db295b8a4ba3de86fee_Traceguids
0x180002885  call    WPP_SF_d
0x18000288a  jmp     short loc_1800028C9
0x18000288c  cmp     [rsp+48h+BytesReturned], 2
0x180002891  jz      short loc_1800028BC
0x180002893  mov     r9d, 8000FFFFh
0x180002899  mov     ebx, r9d
0x18000289c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800028a3  lea     rax, WPP_GLOBAL_Control
0x1800028aa  cmp     rcx, rax
0x1800028ad  jz      short loc_1800028C9
0x1800028af  test    byte ptr [rcx+1Ch], 2
0x1800028b3  jz      short loc_1800028C9
0x1800028b5  mov     edx, 20h ; ' '
0x1800028ba  jmp     short loc_18000287A
0x1800028bc  xor     ecx, ecx
0x1800028be  xor     ebx, ebx
0x1800028c0  cmp     byte ptr [rsp+48h+OutBuffer+1], cl
0x1800028c4  setnz   cl
0x1800028c7  mov     [rdi], ecx
0x1800028c9  mov     rcx, rsi; hObject
0x1800028cc  call    cs:__imp_CloseHandle
0x1800028d2  mov     eax, ebx
0x1800028d4  mov     rbx, [rsp+48h+arg_0]
0x1800028d9  mov     rsi, [rsp+48h+arg_18]
0x1800028de  add     rsp, 40h
0x1800028e2  pop     rdi
0x1800028e3  retn
```
