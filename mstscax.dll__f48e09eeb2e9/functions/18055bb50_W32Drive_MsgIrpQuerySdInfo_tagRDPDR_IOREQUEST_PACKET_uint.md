# W32Drive::MsgIrpQuerySdInfo(tagRDPDR_IOREQUEST_PACKET *,uint)

- ea: `0x18055bb50`
- end: `0x18055bf16`
- name: `?MsgIrpQuerySdInfo@W32Drive@@UEAAXPEAUtagRDPDR_IOREQUEST_PACKET@@I@Z`
- size: `966`
- prototype: `void __fastcall(W32Drive *this, struct tagRDPDR_IOREQUEST_PACKET *)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x18007433c`
- `0x1800745a4`
- `0x180074644`
- `0x18007b16c`
- `0x18012962c`
- `0x18012966c`
- `0x180554ec0`
- `0x18055bb50`
- `0x18055cfc0`
- `0x180688f26`
- `0x18068c010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18055beeb`
- `KERNEL32!CloseHandle` at `0x18055beeb`
- `KERNEL32!LoadLibraryW` at `0x18055bba9`
- `KERNEL32!LoadLibraryW` at `0x18055bba9`
- `KERNEL32!GetLastError` at `0x18055bbf7`
- `KERNEL32!GetLastError` at `0x18055bc66`
- `KERNEL32!GetLastError` at `0x18055bd24`
- `KERNEL32!GetLastError` at `0x18055bd69`
- `KERNEL32!GetLastError` at `0x18055bdc5`
- `KERNEL32!GetLastError` at `0x18055bbf7`
- `KERNEL32!GetLastError` at `0x18055bc66`
- `KERNEL32!GetLastError` at `0x18055bd24`
- `KERNEL32!GetLastError` at `0x18055bd69`
- `KERNEL32!GetLastError` at `0x18055bdc5`
- `KERNEL32!GetProcAddress` at `0x18055bbc5`
- `KERNEL32!GetProcAddress` at `0x18055bbc5`
- `KERNEL32!FreeLibrary` at `0x18055bed8`
- `KERNEL32!FreeLibrary` at `0x18055bed8`
- `KERNEL32!GetCurrentProcess` at `0x18055bbd7`
- `KERNEL32!GetCurrentProcess` at `0x18055bbd7`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x18055bd11`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x18055bd11`
- `ADVAPI32!GetFileSecurityW` at `0x18055bcc1`
- `ADVAPI32!GetFileSecurityW` at `0x18055bd04`
- `ADVAPI32!GetFileSecurityW` at `0x18055bcc1`
- `ADVAPI32!GetFileSecurityW` at `0x18055bd04`

## string_xrefs

- `0x18055bba2`: `ADVAPI32.DLL`
- `0x18055bbbb`: `OpenProcessToken`

## pseudocode

```c
void __fastcall W32Drive::MsgIrpQuerySdInfo(W32Drive *this, struct tagRDPDR_IOREQUEST_PACKET *a2)
{
  __int64 v2; // rcx
  __int64 v4; // rdx
  void *v5; // rbp
  DWORD SecurityDescriptorLength; // r15d
  HMODULE v7; // r14
  LPCWSTR *ObjectW; // r12
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rbx
  HANDLE CurrentProcess; // rax
  const unsigned __int16 *v12; // rdx
  int v13; // r8d
  DWORD LastError; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v16; // rdx
  unsigned int v17; // ebx
  unsigned int v18; // eax
  __int64 v19; // rdx
  unsigned int v20; // eax
  struct tagRDPDR_IOCOMPLETION_PACKET *v21; // rsi
  unsigned int v22; // eax
  DWORD nLengthNeeded; // [rsp+78h] [rbp+10h] BYREF
  HANDLE hObject; // [rsp+88h] [rbp+20h] BYREF

  v2 = *((_QWORD *)this + 8);
  v4 = *((unsigned int *)a2 + 2);
  v5 = 0;
  nLengthNeeded = 0;
  SecurityDescriptorLength = 0;
  hObject = 0;
  v7 = 0;
  ObjectW = (LPCWSTR *)DrObjectMgr<DrFile>::GetObjectW(v2, v4);
  if ( !ObjectW )
  {
    LastError = 2;
    goto LABEL_34;
  }
  if ( (*((_BYTE *)a2 + 24) & 8) != 0 )
  {
    LibraryW = LoadLibraryW(L"ADVAPI32.DLL");
    v7 = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "OpenProcessToken");
      if ( ProcAddress )
      {
        CurrentProcess = GetCurrentProcess();
        if ( !((unsigned int (__fastcall *)(HANDLE, __int64, HANDLE *))ProcAddress)(CurrentProcess, 40, &hObject) )
        {
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_34;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v16 = 96;
          goto LABEL_10;
        }
        if ( !(unsigned int)SetPrivilege(hObject, v12, v13) )
        {
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_34;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v16 = 97;
LABEL_10:
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v16,
            &WPP_8925cfb6df1a32f05c4f5bf12ca5721d_Traceguids,
            CurrentThreadActivityIdPrefix,
            LastError);
LABEL_34:
          v17 = 21;
          goto LABEL_35;
        }
      }
    }
  }
  GetFileSecurityW(ObjectW[16], *((_DWORD *)a2 + 6), 0, 0, &nLengthNeeded);
  if ( nLengthNeeded )
  {
    v5 = operator new(nLengthNeeded);
    if ( v5 )
    {
      if ( GetFileSecurityW(ObjectW[16], *((_DWORD *)a2 + 6), v5, nLengthNeeded, &nLengthNeeded) )
      {
        SecurityDescriptorLength = GetSecurityDescriptorLength(v5);
        LastError = 0;
        v17 = SecurityDescriptorLength + 20;
        goto LABEL_35;
      }
      LastError = GetLastError();
      v17 = 21;
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v18 = RdpWppGetCurrentThreadActivityIdPrefix();
        v19 = 98;
LABEL_32:
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v19,
          &WPP_8925cfb6df1a32f05c4f5bf12ca5721d_Traceguids,
          v18,
          LastError);
      }
    }
    else
    {
      LastError = GetLastError();
      v17 = 21;
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v20 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, &WPP_8925cfb6df1a32f05c4f5bf12ca5721d_Traceguids, v20);
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v17 = 21;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v18 = RdpWppGetCurrentThreadActivityIdPrefix();
      v19 = 100;
      goto LABEL_32;
    }
  }
LABEL_35:
  v21 = DrUTL_AllocIOCompletePacket(a2, v17);
  if ( v21 )
  {
    *((_DWORD *)v21 + 3) = TranslateWinError(LastError);
    *((_DWORD *)v21 + 4) = SecurityDescriptorLength;
    if ( SecurityDescriptorLength )
      memcpy_0((char *)v21 + 20, v5, SecurityDescriptorLength);
    VCManager::ChannelWrite(*(VCManager **)(*((_QWORD *)this + 7) + 224LL), v21, v17);
  }
  else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
         && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v22 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, &WPP_8925cfb6df1a32f05c4f5bf12ca5721d_Traceguids, v22, v17);
  }
  operator delete(a2);
  if ( v5 )
    operator delete(v5);
  if ( v7 )
    FreeLibrary(v7);
  if ( hObject )
    CloseHandle(hObject);
  if ( ObjectW )
    RefCount::Release((RefCount *)ObjectW);
}

```

## disassembly

```asm
0x18055bb50  mov     rax, rsp
0x18055bb53  mov     [rax+18h], rbx
0x18055bb57  mov     [rax+8], rcx
0x18055bb5b  push    rbp
0x18055bb5c  push    rsi
0x18055bb5d  push    rdi
0x18055bb5e  push    r12
0x18055bb60  push    r13
0x18055bb62  push    r14
0x18055bb64  push    r15
0x18055bb66  sub     rsp, 30h
0x18055bb6a  mov     rcx, [rcx+40h]
0x18055bb6e  mov     r13, rdx
0x18055bb71  mov     edx, [rdx+8]
0x18055bb74  xor     ebp, ebp
0x18055bb76  mov     [rax+10h], ebp
0x18055bb79  xor     r15d, r15d
0x18055bb7c  mov     [rax+20h], rbp
0x18055bb80  xor     r14d, r14d
0x18055bb83  call    ?GetObjectW@?$DrObjectMgr@VDrFile@@@@QEAAPEAVDrFile@@K@Z; DrObjectMgr<DrFile>::GetObjectW(ulong)
0x18055bb88  mov     r12, rax
0x18055bb8b  mov     sil, 1
0x18055bb8e  test    rax, rax
0x18055bb91  jz      loc_18055BE19
0x18055bb97  test    byte ptr [r13+18h], 8
0x18055bb9c  jz      loc_18055BCA5
0x18055bba2  lea     rcx, aAdvapi32Dll_3; "ADVAPI32.DLL"
0x18055bba9  call    cs:__imp_LoadLibraryW
0x18055bbaf  mov     r14, rax
0x18055bbb2  test    rax, rax
0x18055bbb5  jz      loc_18055BCA5
0x18055bbbb  lea     rdx, aOpenprocesstok_0; "OpenProcessToken"
0x18055bbc2  mov     rcx, rax; hModule
0x18055bbc5  call    cs:__imp_GetProcAddress
0x18055bbcb  mov     rbx, rax
0x18055bbce  test    rax, rax
0x18055bbd1  jz      loc_18055BCA5
0x18055bbd7  call    cs:__imp_GetCurrentProcess
0x18055bbdd  mov     rcx, rax
0x18055bbe0  lea     r8, [rsp+68h+hObject]
0x18055bbe8  mov     rax, rbx
0x18055bbeb  lea     edx, [rbp+28h]
0x18055bbee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18055bbf3  test    eax, eax
0x18055bbf5  jnz     short loc_18055BC55
0x18055bbf7  call    cs:__imp_GetLastError
0x18055bbfd  mov     edi, eax
0x18055bbff  mov     rax, cs:WPP_GLOBAL_Control
0x18055bc06  lea     rcx, WPP_GLOBAL_Control
0x18055bc0d  cmp     rax, rcx
0x18055bc10  jz      loc_18055BE1E
0x18055bc16  test    [rax+1Ch], sil
0x18055bc1a  jz      loc_18055BE1E
0x18055bc20  cmp     byte ptr [rax+19h], 2
0x18055bc24  jb      loc_18055BE1E
0x18055bc2a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18055bc2f  lea     edx, [rbp+60h]
0x18055bc32  mov     rcx, cs:WPP_GLOBAL_Control
0x18055bc39  lea     r8, WPP_8925cfb6df1a32f05c4f5bf12ca5721d_Traceguids
0x18055bc40  mov     r9d, eax
0x18055bc43  mov     dword ptr [rsp+68h+lpnLengthNeeded], edi
0x18055bc47  mov     rcx, [rcx+10h]
0x18055bc4b  call    WPP_SF_Dd
0x18055bc50  jmp     loc_18055BE1E
0x18055bc55  mov     rcx, [rsp+68h+hObject]; void *
0x18055bc5d  call    ?SetPrivilege@@YAHPEAXPEBGH@Z; SetPrivilege(void *,ushort const *,int)
0x18055bc62  test    eax, eax
0x18055bc64  jnz     short loc_18055BCA5
0x18055bc66  call    cs:__imp_GetLastError
0x18055bc6c  mov     edi, eax
0x18055bc6e  mov     rax, cs:WPP_GLOBAL_Control
0x18055bc75  lea     rcx, WPP_GLOBAL_Control
0x18055bc7c  cmp     rax, rcx
0x18055bc7f  jz      loc_18055BE1E
0x18055bc85  test    [rax+1Ch], sil
0x18055bc89  jz      loc_18055BE1E
0x18055bc8f  cmp     byte ptr [rax+19h], 2
0x18055bc93  jb      loc_18055BE1E
0x18055bc99  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18055bc9e  mov     edx, 61h ; 'a'
0x18055bca3  jmp     short loc_18055BC32
0x18055bca5  mov     edx, [r13+18h]; RequestedInformation
0x18055bca9  lea     rax, [rsp+68h+nLengthNeeded]
0x18055bcae  mov     rcx, [r12+80h]; lpFileName
0x18055bcb6  xor     r9d, r9d; nLength
0x18055bcb9  xor     r8d, r8d; pSecurityDescriptor
0x18055bcbc  mov     [rsp+68h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18055bcc1  call    cs:__imp_GetFileSecurityW
0x18055bcc7  mov     eax, [rsp+68h+nLengthNeeded]
0x18055bccb  test    eax, eax
0x18055bccd  jz      loc_18055BDC5
0x18055bcd3  mov     ecx, eax; Size
0x18055bcd5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18055bcda  mov     rbp, rax
0x18055bcdd  test    rax, rax
0x18055bce0  jz      loc_18055BD69
0x18055bce6  mov     r9d, [rsp+68h+nLengthNeeded]; nLength
0x18055bceb  lea     rax, [rsp+68h+nLengthNeeded]
0x18055bcf0  mov     edx, [r13+18h]; RequestedInformation
0x18055bcf4  mov     r8, rbp; pSecurityDescriptor
0x18055bcf7  mov     rcx, [r12+80h]; lpFileName
0x18055bcff  mov     [rsp+68h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18055bd04  call    cs:__imp_GetFileSecurityW
0x18055bd0a  test    eax, eax
0x18055bd0c  jz      short loc_18055BD24
0x18055bd0e  mov     rcx, rbp; pSecurityDescriptor
0x18055bd11  call    cs:__imp_GetSecurityDescriptorLength
0x18055bd17  mov     r15d, eax
0x18055bd1a  xor     edi, edi
0x18055bd1c  lea     ebx, [rax+14h]
0x18055bd1f  jmp     loc_18055BE23
0x18055bd24  call    cs:__imp_GetLastError
0x18055bd2a  mov     edi, eax
0x18055bd2c  mov     ebx, 15h
0x18055bd31  mov     rax, cs:WPP_GLOBAL_Control
0x18055bd38  lea     rcx, WPP_GLOBAL_Control
0x18055bd3f  cmp     rax, rcx
0x18055bd42  jz      loc_18055BE23
0x18055bd48  test    [rax+1Ch], sil
0x18055bd4c  jz      loc_18055BE23
0x18055bd52  cmp     byte ptr [rax+19h], 4
0x18055bd56  jb      loc_18055BE23
0x18055bd5c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18055bd61  lea     edx, [rbx+4Dh]
0x18055bd64  jmp     loc_18055BDF9
0x18055bd69  call    cs:__imp_GetLastError
0x18055bd6f  mov     edi, eax
0x18055bd71  mov     ebx, 15h
0x18055bd76  mov     rax, cs:WPP_GLOBAL_Control
0x18055bd7d  lea     rcx, WPP_GLOBAL_Control
0x18055bd84  cmp     rax, rcx
0x18055bd87  jz      loc_18055BE23
0x18055bd8d  test    [rax+1Ch], sil
0x18055bd91  jz      loc_18055BE23
0x18055bd97  cmp     byte ptr [rax+19h], 2
0x18055bd9b  jb      loc_18055BE23
0x18055bda1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18055bda6  mov     rcx, cs:WPP_GLOBAL_Control
0x18055bdad  lea     edx, [rbx+4Eh]
0x18055bdb0  mov     r9d, eax
0x18055bdb3  lea     r8, WPP_8925cfb6df1a32f05c4f5bf12ca5721d_Traceguids
0x18055bdba  mov     rcx, [rcx+10h]
0x18055bdbe  call    WPP_SF_d
0x18055bdc3  jmp     short loc_18055BE23
0x18055bdc5  call    cs:__imp_GetLastError
0x18055bdcb  mov     edi, eax
0x18055bdcd  mov     ebx, 15h
0x18055bdd2  mov     rax, cs:WPP_GLOBAL_Control
0x18055bdd9  lea     rcx, WPP_GLOBAL_Control
0x18055bde0  cmp     rax, rcx
0x18055bde3  jz      short loc_18055BE23
0x18055bde5  test    [rax+1Ch], sil
0x18055bde9  jz      short loc_18055BE23
0x18055bdeb  cmp     byte ptr [rax+19h], 4
0x18055bdef  jb      short loc_18055BE23
0x18055bdf1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18055bdf6  lea     edx, [rbx+4Fh]
0x18055bdf9  mov     rcx, cs:WPP_GLOBAL_Control
0x18055be00  lea     r8, WPP_8925cfb6df1a32f05c4f5bf12ca5721d_Traceguids
0x18055be07  mov     r9d, eax
0x18055be0a  mov     dword ptr [rsp+68h+lpnLengthNeeded], edi
0x18055be0e  mov     rcx, [rcx+10h]
0x18055be12  call    WPP_SF_Dd
0x18055be17  jmp     short loc_18055BE23
0x18055be19  mov     edi, 2
0x18055be1e  mov     ebx, 15h
0x18055be23  mov     edx, ebx; unsigned int
0x18055be25  mov     rcx, r13; struct tagRDPDR_IOREQUEST_PACKET *
0x18055be28  call    ?DrUTL_AllocIOCompletePacket@@YAPEAUtagRDPDR_IOCOMPLETION_PACKET@@QEAUtagRDPDR_IOREQUEST_PACKET@@K@Z; DrUTL_AllocIOCompletePacket(tagRDPDR_IOREQUEST_PACKET * const,ulong)
0x18055be2d  mov     rsi, rax
0x18055be30  test    rax, rax
0x18055be33  jz      short loc_18055BE74
0x18055be35  mov     ecx, edi; unsigned int
0x18055be37  call    ?TranslateWinError@@YAJK@Z; TranslateWinError(ulong)
0x18055be3c  mov     [rsi+0Ch], eax
0x18055be3f  mov     [rsi+10h], r15d
0x18055be43  test    r15d, r15d
0x18055be46  jz      short loc_18055BE57
0x18055be48  mov     r8d, r15d; Size
0x18055be4b  lea     rcx, [rsi+14h]; void *
0x18055be4f  mov     rdx, rbp; Src
0x18055be52  call    memcpy_0
0x18055be57  mov     rcx, [rsp+68h+arg_0]
0x18055be5c  mov     r8d, ebx; unsigned int
0x18055be5f  mov     rdx, rsi; void *
0x18055be62  mov     rcx, [rcx+38h]
0x18055be66  mov     rcx, [rcx+0E0h]; this
0x18055be6d  call    ?ChannelWrite@VCManager@@QEAAXPEAXI@Z; VCManager::ChannelWrite(void *,uint)
0x18055be72  jmp     short loc_18055BEBB
0x18055be74  mov     rax, cs:WPP_GLOBAL_Control
0x18055be7b  lea     rcx, WPP_GLOBAL_Control
0x18055be82  cmp     rax, rcx
0x18055be85  jz      short loc_18055BEBB
0x18055be87  test    byte ptr [rax+1Ch], 1
0x18055be8b  jz      short loc_18055BEBB
0x18055be8d  cmp     byte ptr [rax+19h], 2
0x18055be91  jb      short loc_18055BEBB
0x18055be93  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18055be98  mov     rcx, cs:WPP_GLOBAL_Control
0x18055be9f  lea     r8, WPP_8925cfb6df1a32f05c4f5bf12ca5721d_Traceguids
0x18055bea6  mov     edx, 65h ; 'e'
0x18055beab  mov     dword ptr [rsp+68h+lpnLengthNeeded], ebx
0x18055beaf  mov     r9d, eax
0x18055beb2  mov     rcx, [rcx+10h]
0x18055beb6  call    WPP_SF_Dd
0x18055bebb  mov     rcx, r13; Block
0x18055bebe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18055bec3  test    rbp, rbp
0x18055bec6  jz      short loc_18055BED0
0x18055bec8  mov     rcx, rbp; Block
0x18055becb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18055bed0  test    r14, r14
0x18055bed3  jz      short loc_18055BEDE
0x18055bed5  mov     rcx, r14; hLibModule
0x18055bed8  call    cs:__imp_FreeLibrary
0x18055bede  mov     rcx, [rsp+68h+hObject]; hObject
0x18055bee6  test    rcx, rcx
0x18055bee9  jz      short loc_18055BEF1
0x18055beeb  call    cs:__imp_CloseHandle
0x18055bef1  test    r12, r12
0x18055bef4  jz      short loc_18055BEFE
0x18055bef6  mov     rcx, r12; this
0x18055bef9  call    ?Release@RefCount@@QEAAKXZ; RefCount::Release(void)
0x18055befe  mov     rbx, [rsp+68h+arg_10]
0x18055bf06  add     rsp, 30h
0x18055bf0a  pop     r15
0x18055bf0c  pop     r14
0x18055bf0e  pop     r13
0x18055bf10  pop     r12
0x18055bf12  pop     rdi
0x18055bf13  pop     rsi
0x18055bf14  pop     rbp
0x18055bf15  retn
```
