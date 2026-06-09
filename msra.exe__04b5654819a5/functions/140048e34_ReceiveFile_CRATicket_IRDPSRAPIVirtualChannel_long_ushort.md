# ReceiveFile(CRATicket *,IRDPSRAPIVirtualChannel *,long,ushort *)

- ea: `0x140048e34`
- end: `0x1400490cb`
- name: `?ReceiveFile@@YAJPEAVCRATicket@@PEAUIRDPSRAPIVirtualChannel@@JPEAG@Z`
- size: `663`
- prototype: `__int64 __fastcall(ReceivingFileContext **, struct IRDPSRAPIVirtualChannel *, int, unsigned __int16 *Src)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x140047d10`

## callees

- `0x140002156`
- `0x140034ce4`
- `0x140047a04`
- `0x140047b24`
- `0x140048e34`
- `0x140049190`
- `0x1400497dc`

## import_xrefs

- `KERNEL32!WriteFile` at `0x140048ff0`
- `KERNEL32!WriteFile` at `0x140048ff0`
- `msvcrt!malloc` at `0x140048f7c`
- `msvcrt!malloc` at `0x140048f7c`
- `msvcrt!free` at `0x14004903b`
- `msvcrt!free` at `0x14004903b`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140048f69`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140048f69`

## pseudocode

```c
__int64 __fastcall ReceiveFile(
        ReceivingFileContext **a1,
        struct IRDPSRAPIVirtualChannel *a2,
        int a3,
        unsigned __int16 *Src)
{
  unsigned int v5; // ebx
  unsigned int v7; // r9d
  int RecvFileEntry; // edi
  ReceivingFileContext *v9; // rcx
  ReceivingFileContext *v10; // r12
  _DWORD *v11; // rsi
  unsigned int v12; // ebp
  UINT v13; // eax
  size_t v14; // r15
  void *v15; // rax
  char *v16; // r14
  char *v17; // rcx
  unsigned int v18; // ebx
  DWORD v19; // edx
  __int64 v20; // r8
  __int64 v21; // r8
  int v23; // [rsp+30h] [rbp-58h]
  char *v24; // [rsp+38h] [rbp-50h]
  HANDLE hFile; // [rsp+40h] [rbp-48h]
  LPCVOID lpBuffer; // [rsp+90h] [rbp+8h] BYREF
  unsigned int v27; // [rsp+A0h] [rbp+18h]

  v27 = a3;
  v5 = a3;
  lpBuffer = 0;
  if ( !a2 )
  {
    v7 = 825;
LABEL_3:
    RecvFileEntry = -2147467261;
    CEventLogger::LogError(
      (CEventLogger *)a1,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\core\\lib\\rarecv.cpp",
      v7,
      L"ReceiveFile",
      0x80004003);
    return (unsigned int)RecvFileEntry;
  }
  if ( !Src )
  {
    v7 = 826;
    goto LABEL_3;
  }
  v9 = a1[64];
  if ( !v9 )
    return (unsigned int)-2147418113;
  v10 = a1[60];
  RecvFileEntry = ReceivingFileContext::GetRecvFileEntry(v9, a3, a2, 1, (struct RECV_ENTRY **)&lpBuffer);
  v11 = lpBuffer;
  if ( RecvFileEntry < 0 )
    goto LABEL_34;
  if ( !lpBuffer || *((_DWORD *)lpBuffer + 8) == 8 )
    return (unsigned int)RecvFileEntry;
  if ( *((_QWORD *)lpBuffer + 3) )
    goto LABEL_17;
  if ( *((int *)lpBuffer + 8) <= 0 )
  {
    RecvFileEntry = GetNewFile((struct CRATicket *)a1, (struct RECV_ENTRY *)lpBuffer, v5);
    if ( RecvFileEntry < 0 )
    {
      v11[8] = 8;
      goto LABEL_34;
    }
    v11[8] = 1;
LABEL_17:
    v12 = 0;
    hFile = (HANDLE)*((_QWORD *)v11 + 3);
    if ( hFile )
    {
      v13 = SysStringByteLen(Src);
      v14 = v13;
      v15 = malloc(v13 + 1);
      lpBuffer = v15;
      if ( v15 )
      {
        RecvFileEntry = 0;
        memcpy_0(v15, Src, v14);
        v16 = (char *)lpBuffer;
        *((_BYTE *)lpBuffer + v14) = 0;
        LODWORD(lpBuffer) = 0;
        v17 = v16;
        v24 = v16;
        v18 = 0;
        v19 = v14;
        v23 = v14;
        if ( (_DWORD)v14 )
        {
          while ( WriteFile(hFile, v17, v19, (LPDWORD)&lpBuffer, 0) )
          {
            if ( !(_DWORD)lpBuffer )
            {
              v12 = v18;
              break;
            }
            v18 += (unsigned int)lpBuffer;
            v19 = v23 - (_DWORD)lpBuffer;
            v23 -= (int)lpBuffer;
            v17 = &v24[(unsigned int)lpBuffer];
            v24 = v17;
            if ( v18 >= (unsigned int)v14 )
            {
              v12 = v18;
              goto LABEL_29;
            }
          }
          RecvFileEntry = -2147467259;
        }
        else
        {
          v12 = 0;
        }
LABEL_29:
        free(v16);
        if ( RecvFileEntry < 0 )
        {
          v5 = v27;
        }
        else
        {
          v11[9] += v12;
          if ( !v10 )
            return (unsigned int)RecvFileEntry;
          v5 = v27;
          RecvFileEntry = FileReceiveAgent::ReturnFileToReceivers(v10, v27, v20, v11, 13);
          if ( RecvFileEntry >= 0 )
            return (unsigned int)RecvFileEntry;
        }
      }
      else
      {
        RecvFileEntry = -2147024882;
      }
    }
    else
    {
      RecvFileEntry = -2147024890;
    }
    goto LABEL_34;
  }
  *((_DWORD *)lpBuffer + 8) = 8;
  RecvFileEntry = -2147467259;
LABEL_34:
  if ( v11 )
  {
    AbortReceiver((struct CRATicket *)a1, (struct RECV_ENTRY *)v11, 1);
    if ( v10 )
      return (unsigned int)FileReceiveAgent::ReturnFileToReceivers(v10, v5, v21, v11, 8);
  }
  return (unsigned int)RecvFileEntry;
}

```

## disassembly

```asm
0x140048e34  mov     rax, rsp
0x140048e37  mov     [rax+10h], rbx
0x140048e3b  mov     [rax+18h], r8d
0x140048e3f  push    rbp
0x140048e40  push    rsi
0x140048e41  push    rdi
0x140048e42  push    r12
0x140048e44  push    r13
0x140048e46  push    r14
0x140048e48  push    r15
0x140048e4a  sub     rsp, 50h
0x140048e4e  mov     r14, r9
0x140048e51  mov     ebx, r8d
0x140048e54  mov     r13, rcx
0x140048e57  mov     qword ptr [rax+8], 0
0x140048e5f  test    rdx, rdx
0x140048e62  jnz     short loc_140048E9B
0x140048e64  mov     r9d, 339h; unsigned int
0x140048e6a  mov     [rsp+88h+var_60], 80004003h; unsigned int
0x140048e72  lea     rax, aReceivefile; "ReceiveFile"
0x140048e79  mov     [rsp+88h+lpOverlapped], rax; unsigned __int16 *
0x140048e7e  mov     edi, 80004003h
0x140048e83  lea     r8, aBaseDiagnosisR; "base\\diagnosis\\ra\\core\\lib\\rarecv."...
0x140048e8a  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140048e91  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140048e96  jmp     loc_1400490B0
0x140048e9b  test    r14, r14
0x140048e9e  jnz     short loc_140048EA8
0x140048ea0  mov     r9d, 33Ah
0x140048ea6  jmp     short loc_140048E6A
0x140048ea8  mov     rcx, [rcx+200h]; this
0x140048eaf  test    rcx, rcx
0x140048eb2  jnz     short loc_140048EBE
0x140048eb4  mov     edi, 8000FFFFh
0x140048eb9  jmp     loc_1400490B0
0x140048ebe  mov     r12, [r13+1E0h]
0x140048ec5  lea     rax, [rsp+88h+lpBuffer]
0x140048ecd  mov     [rsp+88h+lpOverlapped], rax; struct RECV_ENTRY **
0x140048ed2  mov     r9d, 1; int
0x140048ed8  mov     r8, rdx; struct IRDPSRAPIVirtualChannel *
0x140048edb  mov     edx, ebx; int
0x140048edd  call    ?GetRecvFileEntry@ReceivingFileContext@@QEAAJJPEAUIRDPSRAPIVirtualChannel@@HPEAPEAURECV_ENTRY@@@Z; ReceivingFileContext::GetRecvFileEntry(long,IRDPSRAPIVirtualChannel *,int,RECV_ENTRY * *)
0x140048ee2  mov     edi, eax
0x140048ee4  mov     rsi, [rsp+88h+lpBuffer]
0x140048eec  test    eax, eax
0x140048eee  js      loc_14004907E
0x140048ef4  test    rsi, rsi
0x140048ef7  jz      loc_1400490B0
0x140048efd  cmp     dword ptr [rsi+20h], 8
0x140048f01  jz      loc_1400490B0
0x140048f07  cmp     qword ptr [rsi+18h], 0
0x140048f0c  jnz     short loc_140048F4C
0x140048f0e  cmp     dword ptr [rsi+20h], 0
0x140048f12  jle     short loc_140048F25
0x140048f14  mov     dword ptr [rsi+20h], 8
0x140048f1b  mov     edi, 80004005h
0x140048f20  jmp     loc_14004907E
0x140048f25  mov     r8d, ebx; int
0x140048f28  mov     rdx, rsi; struct RECV_ENTRY *
0x140048f2b  mov     rcx, r13; struct CRATicket *
0x140048f2e  call    ?GetNewFile@@YAJPEAVCRATicket@@PEAURECV_ENTRY@@J@Z; GetNewFile(CRATicket *,RECV_ENTRY *,long)
0x140048f33  mov     edi, eax
0x140048f35  test    eax, eax
0x140048f37  jns     short loc_140048F45
0x140048f39  mov     dword ptr [rsi+20h], 8
0x140048f40  jmp     loc_14004907E
0x140048f45  mov     dword ptr [rsi+20h], 1
0x140048f4c  xor     ebp, ebp
0x140048f4e  mov     rax, [rsi+18h]
0x140048f52  mov     [rsp+88h+hFile], rax
0x140048f57  test    rax, rax
0x140048f5a  jnz     short loc_140048F66
0x140048f5c  mov     edi, 80070006h
0x140048f61  jmp     loc_14004907E
0x140048f66  mov     rcx, r14; bstr
0x140048f69  call    cs:__imp_SysStringByteLen
0x140048f70  nop     dword ptr [rax+rax+00h]
0x140048f75  mov     r15d, eax
0x140048f78  lea     ecx, [r15+1]; Size
0x140048f7c  call    cs:__imp_malloc
0x140048f83  nop     dword ptr [rax+rax+00h]
0x140048f88  mov     [rsp+88h+lpBuffer], rax
0x140048f90  test    rax, rax
0x140048f93  jnz     short loc_140048F9F
0x140048f95  mov     edi, 8007000Eh
0x140048f9a  jmp     loc_14004907E
0x140048f9f  xor     edi, edi
0x140048fa1  mov     r8, r15; Size
0x140048fa4  mov     rdx, r14; Src
0x140048fa7  mov     rcx, rax; void *
0x140048faa  call    memcpy_0
0x140048faf  mov     r14, [rsp+88h+lpBuffer]
0x140048fb7  mov     [r15+r14], dil
0x140048fbb  mov     dword ptr [rsp+88h+lpBuffer], edi
0x140048fc2  mov     rcx, r14
0x140048fc5  mov     [rsp+88h+var_50], rcx
0x140048fca  xor     ebx, ebx
0x140048fcc  mov     edx, r15d
0x140048fcf  mov     [rsp+88h+var_58], edx
0x140048fd3  test    r15d, r15d
0x140048fd6  jz      short loc_140049036
0x140048fd8  mov     [rsp+88h+lpOverlapped], rdi; lpOverlapped
0x140048fdd  lea     r9, [rsp+88h+lpBuffer]; lpNumberOfBytesWritten
0x140048fe5  mov     r8d, edx; nNumberOfBytesToWrite
0x140048fe8  mov     rdx, rcx; lpBuffer
0x140048feb  mov     rcx, [rsp+88h+hFile]; hFile
0x140048ff0  call    cs:__imp_WriteFile
0x140048ff7  nop     dword ptr [rax+rax+00h]
0x140048ffc  test    eax, eax
0x140048ffe  jz      short loc_14004902F
0x140049000  mov     eax, dword ptr [rsp+88h+lpBuffer]
0x140049007  test    eax, eax
0x140049009  jz      short loc_14004902D
0x14004900b  add     ebx, eax
0x14004900d  mov     edx, [rsp+88h+var_58]
0x140049011  sub     edx, eax
0x140049013  mov     [rsp+88h+var_58], edx
0x140049017  mov     rcx, [rsp+88h+var_50]
0x14004901c  add     rcx, rax
0x14004901f  mov     [rsp+88h+var_50], rcx
0x140049024  cmp     ebx, r15d
0x140049027  jb      short loc_140048FD8
0x140049029  mov     ebp, ebx
0x14004902b  jmp     short loc_140049038
0x14004902d  mov     ebp, ebx
0x14004902f  mov     edi, 80004005h
0x140049034  jmp     short loc_140049038
0x140049036  xor     ebp, ebp
0x140049038  mov     rcx, r14; Block
0x14004903b  call    cs:__imp_free
0x140049042  nop     dword ptr [rax+rax+00h]
0x140049047  test    edi, edi
0x140049049  js      short loc_140049077
0x14004904b  add     [rsi+24h], ebp
0x14004904e  test    r12, r12
0x140049051  jz      short loc_1400490B0
0x140049053  mov     dword ptr [rsp+88h+lpOverlapped], 0Dh
0x14004905b  mov     r9, rsi
0x14004905e  mov     ebx, [rsp+88h+arg_10]
0x140049065  mov     edx, ebx
0x140049067  mov     rcx, r12
0x14004906a  call    ?ReturnFileToReceivers@FileReceiveAgent@@QEAAJJPEAUIRDPSRAPIVirtualChannel@@PEAURECV_ENTRY@@W4RAFX_STATUS@@@Z; FileReceiveAgent::ReturnFileToReceivers(long,IRDPSRAPIVirtualChannel *,RECV_ENTRY *,RAFX_STATUS)
0x14004906f  mov     edi, eax
0x140049071  test    eax, eax
0x140049073  jns     short loc_1400490B0
0x140049075  jmp     short loc_14004907E
0x140049077  mov     ebx, [rsp+88h+arg_10]
0x14004907e  test    rsi, rsi
0x140049081  jz      short loc_1400490B0
0x140049083  mov     r8d, 1; int
0x140049089  mov     rdx, rsi; struct RECV_ENTRY *
0x14004908c  mov     rcx, r13; struct CRATicket *
0x14004908f  call    ?AbortReceiver@@YAJPEAVCRATicket@@PEAURECV_ENTRY@@H@Z; AbortReceiver(CRATicket *,RECV_ENTRY *,int)
0x140049094  test    r12, r12
0x140049097  jz      short loc_1400490B0
0x140049099  mov     dword ptr [rsp+88h+lpOverlapped], 8
0x1400490a1  mov     r9, rsi
0x1400490a4  mov     edx, ebx
0x1400490a6  mov     rcx, r12
0x1400490a9  call    ?ReturnFileToReceivers@FileReceiveAgent@@QEAAJJPEAUIRDPSRAPIVirtualChannel@@PEAURECV_ENTRY@@W4RAFX_STATUS@@@Z; FileReceiveAgent::ReturnFileToReceivers(long,IRDPSRAPIVirtualChannel *,RECV_ENTRY *,RAFX_STATUS)
0x1400490ae  mov     edi, eax
0x1400490b0  mov     eax, edi
0x1400490b2  mov     rbx, [rsp+88h+arg_8]
0x1400490ba  add     rsp, 50h
0x1400490be  pop     r15
0x1400490c0  pop     r14
0x1400490c2  pop     r13
0x1400490c4  pop     r12
0x1400490c6  pop     rdi
0x1400490c7  pop     rsi
0x1400490c8  pop     rbp
0x1400490c9  retn
```
