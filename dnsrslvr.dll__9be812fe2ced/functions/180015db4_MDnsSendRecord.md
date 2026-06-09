# MDnsSendRecord

- ea: `0x180015db4`
- end: `0x180015f35`
- name: `MDnsSendRecord`
- size: `385`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180016778`

## callees

- `0x180011c24`
- `0x180015db4`
- `0x180015f3c`
- `0x18003aa8c`
- `0x18003ae2c`
- `0x18003aef8`
- `0x18003b3d8`
- `0x180086b1c`

## import_xrefs

- `DNSAPI!DnsRecordCopyEx` at `0x180015e31`
- `DNSAPI!DnsRecordCopyEx` at `0x180015e31`
- `DNSAPI!DnsFree` at `0x180015ea6`
- `DNSAPI!DnsFree` at `0x180015ec4`
- `DNSAPI!DnsFree` at `0x180015ea6`
- `DNSAPI!DnsFree` at `0x180015ec4`

## pseudocode

```c
__int64 __fastcall MDnsSendRecord(struct _DnsNetInfo *a1, PDNS_RECORD pRecord, __int64 a3, __int64 a4, int a5)
{
  __int64 MsgBuf; // rdi
  unsigned int v9; // ebx
  __int64 v10; // rsi
  char *v11; // r15
  struct _DnsRecordW *v12; // rax
  struct _DnsRecordW *v13; // rbp
  unsigned int v14; // eax
  __int64 v16; // rdx

  if ( !pRecord || !a3 )
    return 87;
  MsgBuf = Packet_AllocateMsgBuf(0xFFFF);
  if ( !MsgBuf )
    return 14;
  v9 = 0;
  v10 = 0;
  *(_DWORD *)(MsgBuf + 664) = a5;
  while ( 1 )
  {
    if ( (unsigned int)v10 >= *((_DWORD *)a1 + 17) )
      goto LABEL_15;
    v11 = (char *)a1 + 160 * v10 + 104;
    if ( !v11 )
      goto LABEL_12;
    v12 = (struct _DnsRecordW *)DnsRecordCopyEx(pRecord, DnsCharSetUnicode, DnsCharSetUnicode);
    v13 = v12;
    if ( !v12 )
      break;
    v14 = PostProcessRecords(a1, *((_DWORD *)v11 + 12), 1, v12);
    v9 = v14;
    if ( v14 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
        goto LABEL_14;
      v16 = 52;
      goto LABEL_24;
    }
    Packet_InitializeMsgBuf(MsgBuf);
    *(_BYTE *)(MsgBuf + 702) = *(_BYTE *)(MsgBuf + 702) & 3 | 0x84;
    v14 = Packet_AddRecordsToMessage(MsgBuf, v13);
    v9 = v14;
    if ( v14 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
        goto LABEL_14;
      v16 = 53;
      goto LABEL_24;
    }
    v14 = MDnsSendMessage(MsgBuf, a3);
    v9 = v14;
    if ( v14 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      {
LABEL_14:
        DnsFree(v13, DnsFreeRecordList);
        goto LABEL_15;
      }
      v16 = 54;
LABEL_24:
      WPP_SF_d(1035, v16, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids, v14);
      goto LABEL_14;
    }
    DnsFree(v13, DnsFreeRecordList);
LABEL_12:
    v10 = (unsigned int)(v10 + 1);
  }
  v9 = 14;
LABEL_15:
  Packet_FreeMsgBuf((char *)MsgBuf);
  return v9;
}

```

## disassembly

```asm
0x180015db4  push    rbx
0x180015db6  push    rbp
0x180015db7  push    rsi
0x180015db8  push    rdi
0x180015db9  push    r12
0x180015dbb  push    r13
0x180015dbd  push    r14
0x180015dbf  push    r15
0x180015dc1  sub     rsp, 28h
0x180015dc5  mov     r12, r8
0x180015dc8  mov     r13, rdx
0x180015dcb  mov     r14, rcx
0x180015dce  test    rdx, rdx
0x180015dd1  jz      loc_180015EE5
0x180015dd7  test    r8, r8
0x180015dda  jz      loc_180015EE5
0x180015de0  mov     ecx, 0FFFFh
0x180015de5  call    Packet_AllocateMsgBuf
0x180015dea  mov     rdi, rax
0x180015ded  test    rax, rax
0x180015df0  jz      loc_180015EEC
0x180015df6  mov     eax, [rsp+68h+arg_20]
0x180015dfd  xor     ebx, ebx
0x180015dff  xor     esi, esi
0x180015e01  mov     [rdi+298h], eax
0x180015e07  cmp     esi, [r14+44h]
0x180015e0b  jnb     loc_180015ECA
0x180015e11  lea     r15, [rsi+rsi*4]
0x180015e15  shl     r15, 5
0x180015e19  add     r15, 68h ; 'h'
0x180015e1d  add     r15, r14
0x180015e20  jz      loc_180015EAC
0x180015e26  mov     edx, 1; CharSetIn
0x180015e2b  mov     rcx, r13; pRecord
0x180015e2e  mov     r8d, edx; CharSetOut
0x180015e31  call    cs:__imp_DnsRecordCopyEx
0x180015e37  mov     rbp, rax
0x180015e3a  test    rax, rax
0x180015e3d  jz      loc_180015F2E
0x180015e43  mov     edx, [r15+30h]; unsigned int
0x180015e47  mov     r9, rax; struct _DnsRecordW *
0x180015e4a  mov     r8d, 1; int
0x180015e50  mov     rcx, r14; struct _DnsNetInfo *
0x180015e53  call    ?PostProcessRecords@@YAJPEAU_DnsNetInfo@@KHPEAU_DnsRecordW@@@Z; PostProcessRecords(_DnsNetInfo *,ulong,int,_DnsRecordW *)
0x180015e58  mov     ebx, eax
0x180015e5a  test    eax, eax
0x180015e5c  jnz     loc_180015F0A
0x180015e62  mov     rcx, rdi
0x180015e65  call    Packet_InitializeMsgBuf
0x180015e6a  mov     al, [rdi+2BEh]
0x180015e70  mov     rdx, rbp
0x180015e73  and     al, 3
0x180015e75  mov     rcx, rdi
0x180015e78  or      al, 84h
0x180015e7a  mov     [rdi+2BEh], al
0x180015e80  call    Packet_AddRecordsToMessage
0x180015e85  mov     ebx, eax
0x180015e87  test    eax, eax
0x180015e89  jnz     short loc_180015EFA
0x180015e8b  mov     r8d, [r15+30h]
0x180015e8f  mov     rdx, r12
0x180015e92  mov     rcx, rdi
0x180015e95  call    MDnsSendMessage
0x180015e9a  mov     ebx, eax
0x180015e9c  test    eax, eax
0x180015e9e  jnz     short loc_180015EB3
0x180015ea0  lea     edx, [rax+1]; FreeType
0x180015ea3  mov     rcx, rbp; pData
0x180015ea6  call    cs:__imp_DnsFree
0x180015eac  inc     esi
0x180015eae  jmp     loc_180015E07
0x180015eb3  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180015eba  jnz     short loc_180015EF3
0x180015ebc  mov     edx, 1; FreeType
0x180015ec1  mov     rcx, rbp; pData
0x180015ec4  call    cs:__imp_DnsFree
0x180015eca  mov     rcx, rdi; void *
0x180015ecd  call    Packet_FreeMsgBuf
0x180015ed2  mov     eax, ebx
0x180015ed4  add     rsp, 28h
0x180015ed8  pop     r15
0x180015eda  pop     r14
0x180015edc  pop     r13
0x180015ede  pop     r12
0x180015ee0  pop     rdi
0x180015ee1  pop     rsi
0x180015ee2  pop     rbp
0x180015ee3  pop     rbx
0x180015ee4  retn
0x180015ee5  mov     ebx, 57h ; 'W'
0x180015eea  jmp     short loc_180015ED2
0x180015eec  mov     ebx, 0Eh
0x180015ef1  jmp     short loc_180015ED2
0x180015ef3  mov     edx, 36h ; '6'
0x180015ef8  jmp     short loc_180015F18
0x180015efa  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180015f01  jz      short loc_180015EBC
0x180015f03  mov     edx, 35h ; '5'
0x180015f08  jmp     short loc_180015F18
0x180015f0a  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180015f11  jz      short loc_180015EBC
0x180015f13  mov     edx, 34h ; '4'
0x180015f18  mov     r9d, eax
0x180015f1b  lea     r8, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids
0x180015f22  mov     ecx, 40Bh
0x180015f27  call    WPP_SF_d
0x180015f2c  jmp     short loc_180015EBC
0x180015f2e  mov     ebx, 0Eh
0x180015f33  jmp     short loc_180015ECA
```
