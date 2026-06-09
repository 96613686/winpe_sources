# TLSLogger::SaveTLSRecord(void *,ulong,uchar *,ulong)

- ea: `0x18015eb70`
- end: `0x18015eea8`
- name: `?SaveTLSRecord@TLSLogger@@AEAAXPEAXKPEAEK@Z`
- size: `824`
- prototype: `void(TLSLogger *__hidden this, void *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18015ea00`

## callees

- `0x180078c20`
- `0x18015e91c`
- `0x18015eb70`
- `0x18015ef58`
- `0x18015efd8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18015edf6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18015ee27`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18015ee5e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18015ee84`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18015edf6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18015ee27`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18015ee5e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18015ee84`

## string_xrefs

- `0x18015ed4e`: `Record #%d, TLS %d.%d, Content: Alert, Size: %d, AlertLevel: %d, AlertCode: %d, Corrupt or incomplete: %s\n`
- `0x18015ed75`: `Record #%d, TLS %d.%d, Content: ChangeCipherSpec, Size: %d, Corrupt or incomplete: %s\n`
- `0x18015ecbc`: `Record #%d, TLS %d.%d, Content: Application, Size: %d, Corrupt or incomplete: %s\n`
- `0x18015ecb0`: `Record #%d, TLS %d.%d, Content: Heartbeat, Size: %d, Corrupt or incomplete: %s\n`
- `0x18015ed0b`: `Record #%d, TLS %d.%d, Content: Handshake, Size: %d, Handshake message type: %d (%s), Corrupt or incomplete: %s\n`
- `0x18015ec90`: `Record #%d, TLS %d.%d, Content: Unknown(%d), Size: %d, Corrupt or incomplete: %s\n`

## pseudocode

```c
void __fastcall TLSLogger::SaveTLSRecord(
        TLSLogger *this,
        void *a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int a5)
{
  const char *v8; // r10
  int v9; // edx
  __int64 v10; // r9
  int v11; // ecx
  const char *v12; // r8
  __int64 v13; // rax
  unsigned __int8 *v14; // r10
  int v15; // r9d
  const char *v16; // r8
  __int64 v17; // rdx
  char *v18; // rax
  unsigned int i; // ebx
  LPOVERLAPPED lpOverlapped; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v21; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v22; // [rsp+30h] [rbp-D0h]
  unsigned __int8 *v23; // [rsp+38h] [rbp-C8h]
  unsigned __int8 *v24; // [rsp+40h] [rbp-C0h]
  unsigned __int8 *v25; // [rsp+48h] [rbp-B8h]
  unsigned __int8 v26; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int8 v27[3]; // [rsp+61h] [rbp-9Fh] BYREF
  char v28[2]; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned __int8 v29; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int8 v30; // [rsp+69h] [rbp-97h] BYREF
  unsigned __int8 v31; // [rsp+6Ah] [rbp-96h] BYREF
  unsigned __int8 v32; // [rsp+6Bh] [rbp-95h] BYREF
  int v33; // [rsp+6Ch] [rbp-94h] BYREF
  char Buffer[512]; // [rsp+70h] [rbp-90h] BYREF

  v33 = 1;
  v29 = 0;
  v27[0] = 0;
  v26 = 0;
  *(_WORD *)v28 = 0;
  v30 = 0;
  v32 = 0;
  v31 = 0;
  TLSLogger::ParseTLSRecord(this, a4, a5, &v29, v27, &v26, (unsigned __int16 *)v28, &v30, &v32, &v31, &v33);
  v8 = "YES";
  switch ( v29 )
  {
    case 0x14u:
      v9 = v27[0];
      v12 = "Record #%d, TLS %d.%d, Content: ChangeCipherSpec, Size: %d, Corrupt or incomplete: %s\r\n";
      v10 = a3;
      goto LABEL_17;
    case 0x15u:
      if ( !v33 )
        v8 = "NO";
      v25 = (unsigned __int8 *)v8;
      LODWORD(v24) = v31;
      LODWORD(v23) = v32;
      LODWORD(v22) = *(unsigned __int16 *)v28;
      LODWORD(v21) = v26;
      v16 = "Record #%d, TLS %d.%d, Content: Alert, Size: %d, AlertLevel: %d, AlertCode: %d, Corrupt or incomplete: %s\r\n";
      LODWORD(lpOverlapped) = v27[0];
      goto LABEL_15;
    case 0x16u:
      v13 = TLSLogger::TLSHandshakeMessageTypeToString((unsigned int)v29 - 22, v30);
      v25 = v14;
      v24 = (unsigned __int8 *)v13;
      LODWORD(v23) = v15;
      LODWORD(v22) = *(unsigned __int16 *)v28;
      LODWORD(v21) = v26;
      LODWORD(lpOverlapped) = v27[0];
      v16 = "Record #%d, TLS %d.%d, Content: Handshake, Size: %d, Handshake message type: %d (%s), Corrupt or incomplete: %s\r\n";
LABEL_15:
      StringCbPrintfA(Buffer, 0x1F4u, v16, a3, lpOverlapped, v21, v22, v23, v24, v25);
      goto LABEL_21;
  }
  v9 = v27[0];
  v10 = a3;
  if ( v29 == 23 )
  {
    v12 = "Record #%d, TLS %d.%d, Content: Application, Size: %d, Corrupt or incomplete: %s\r\n";
LABEL_17:
    v11 = v26;
    goto LABEL_18;
  }
  v11 = v26;
  if ( v29 != 24 )
  {
    if ( !v33 )
      v8 = "NO";
    StringCbPrintfA(
      Buffer,
      0x1F4u,
      "Record #%d, TLS %d.%d, Content: Unknown(%d), Size: %d, Corrupt or incomplete: %s\r\n",
      a3,
      v27[0],
      v26,
      v29,
      *(unsigned __int16 *)v28,
      v8);
    goto LABEL_21;
  }
  v12 = "Record #%d, TLS %d.%d, Content: Heartbeat, Size: %d, Corrupt or incomplete: %s\r\n";
LABEL_18:
  if ( !v33 )
    v8 = "NO";
  LODWORD(v22) = *(unsigned __int16 *)v28;
  LODWORD(v21) = v11;
  LODWORD(lpOverlapped) = v9;
  StringCbPrintfA(Buffer, 0x1F4u, v12, v10, lpOverlapped, v21, v22, v8);
LABEL_21:
  v17 = 500;
  v18 = Buffer;
  do
  {
    if ( !*v18 )
      break;
    ++v18;
    --v17;
  }
  while ( v17 );
  WriteFile(a2, Buffer, v17 != 0 ? 500 - v17 + 1 : 1, 0, 0);
  for ( i = 0; i < a5; ++i )
  {
    if ( i && (i & 0x3F) == 0 )
      WriteFile(a2, "\r\n", 3u, 0, 0);
    StringCbPrintfA(v28, 3u, "%02X ", a4[i]);
    WriteFile(a2, v28, 3u, 0, 0);
  }
  WriteFile(a2, "\r\n\r\n", 5u, 0, 0);
}

```

## disassembly

```asm
0x18015eb70  push    rbp
0x18015eb72  push    rbx
0x18015eb73  push    rdi
0x18015eb74  push    r14
0x18015eb76  push    r15
0x18015eb78  lea     rbp, [rsp-180h]
0x18015eb80  sub     rsp, 280h
0x18015eb87  mov     rax, cs:__security_cookie
0x18015eb8e  xor     rax, rsp
0x18015eb91  mov     [rbp+1A0h+var_30], rax
0x18015eb98  xor     r15d, r15d
0x18015eb9b  mov     [rsp+2A0h+var_234], 1
0x18015eba3  mov     r14, r9
0x18015eba6  mov     [rsp+2A0h+var_238], r15b
0x18015ebab  lea     rax, [rsp+2A0h+var_234]
0x18015ebb0  mov     [rsp+2A0h+var_23F], r15b
0x18015ebb5  mov     [rsp+2A0h+var_250], rax; int *
0x18015ebba  lea     r9, [rsp+2A0h+var_238]; unsigned __int8 *
0x18015ebbf  lea     rax, [rsp+2A0h+var_236]
0x18015ebc4  mov     [rsp+2A0h+var_240], r15b
0x18015ebc9  mov     [rsp+2A0h+var_258], rax; unsigned __int8 *
0x18015ebce  mov     rdi, rdx
0x18015ebd1  lea     rax, [rsp+2A0h+var_235]
0x18015ebd6  mov     word ptr [rsp+2A0h+var_23C], r15w
0x18015ebdc  mov     [rsp+2A0h+var_260], rax; unsigned __int8 *
0x18015ebe1  mov     ebx, r8d
0x18015ebe4  mov     r8d, [rbp+1A0h+arg_20]; unsigned int
0x18015ebeb  lea     rax, [rsp+2A0h+var_237]
0x18015ebf0  mov     [rsp+2A0h+var_268], rax; unsigned __int8 *
0x18015ebf5  mov     rdx, r14; unsigned __int8 *
0x18015ebf8  lea     rax, [rsp+2A0h+var_23C]
0x18015ebfd  mov     [rsp+2A0h+var_237], r15b
0x18015ec02  mov     [rsp+2A0h+var_270], rax; unsigned __int16 *
0x18015ec07  lea     rax, [rsp+2A0h+var_240]
0x18015ec0c  mov     [rsp+2A0h+var_278], rax; unsigned __int8 *
0x18015ec11  lea     rax, [rsp+2A0h+var_23F]
0x18015ec16  mov     [rsp+2A0h+lpOverlapped], rax; unsigned __int8 *
0x18015ec1b  mov     [rsp+2A0h+var_235], r15b
0x18015ec20  mov     [rsp+2A0h+var_236], r15b
0x18015ec25  call    ?ParseTLSRecord@TLSLogger@@AEAAXPEAEK000PEAG000PEAH@Z; TLSLogger::ParseTLSRecord(uchar *,ulong,uchar *,uchar *,uchar *,ushort *,uchar *,uchar *,uchar *,int *)
0x18015ec2a  movzx   r8d, [rsp+2A0h+var_238]
0x18015ec30  lea     r10, aYes; "YES"
0x18015ec37  mov     ecx, r8d
0x18015ec3a  lea     rax, aNo; "NO"
0x18015ec41  sub     ecx, 14h
0x18015ec44  jz      loc_18015ED70
0x18015ec4a  sub     ecx, 1
0x18015ec4d  jz      loc_18015ED14
0x18015ec53  sub     ecx, 1
0x18015ec56  jz      short loc_18015ECC8
0x18015ec58  movzx   edx, [rsp+2A0h+var_23F]
0x18015ec5d  mov     r9d, ebx
0x18015ec60  mov     ebx, 1F4h
0x18015ec65  sub     ecx, 1
0x18015ec68  jz      short loc_18015ECBC
0x18015ec6a  cmp     ecx, 1
0x18015ec6d  movzx   ecx, [rsp+2A0h+var_240]
0x18015ec72  jz      short loc_18015ECB0
0x18015ec74  cmp     [rsp+2A0h+var_234], r15d
0x18015ec79  cmovz   r10, rax
0x18015ec7d  movzx   eax, word ptr [rsp+2A0h+var_23C]
0x18015ec82  mov     [rsp+2A0h+var_260], r10
0x18015ec87  mov     dword ptr [rsp+2A0h+var_268], eax
0x18015ec8b  mov     dword ptr [rsp+2A0h+var_270], r8d
0x18015ec90  lea     r8, aRecordDTlsDDCo; "Record #%d, TLS %d.%d, Content: Unknown"...
0x18015ec97  mov     dword ptr [rsp+2A0h+var_278], ecx
0x18015ec9b  lea     rcx, [rsp+2A0h+Buffer]; char *
0x18015eca0  mov     dword ptr [rsp+2A0h+lpOverlapped], edx
0x18015eca4  mov     edx, ebx; unsigned __int64
0x18015eca6  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x18015ecab  jmp     loc_18015EDB5
0x18015ecb0  lea     r8, aRecordDTlsDDCo_2; "Record #%d, TLS %d.%d, Content: Heartbe"...
0x18015ecb7  jmp     loc_18015ED89
0x18015ecbc  lea     r8, aRecordDTlsDDCo_0; "Record #%d, TLS %d.%d, Content: Applica"...
0x18015ecc3  jmp     loc_18015ED84
0x18015ecc8  cmp     [rsp+2A0h+var_234], r15d
0x18015eccd  movzx   r9d, [rsp+2A0h+var_237]
0x18015ecd3  mov     edx, r9d
0x18015ecd6  cmovz   r10, rax
0x18015ecda  call    ?TLSHandshakeMessageTypeToString@TLSLogger@@AEAAPEBDW4TLSHandshakeMessageTypes@@@Z; TLSLogger::TLSHandshakeMessageTypeToString(TLSHandshakeMessageTypes)
0x18015ecdf  movzx   r8d, [rsp+2A0h+var_23F]
0x18015ece5  movzx   ecx, word ptr [rsp+2A0h+var_23C]
0x18015ecea  movzx   edx, [rsp+2A0h+var_240]
0x18015ecef  mov     [rsp+2A0h+var_258], r10
0x18015ecf4  mov     [rsp+2A0h+var_260], rax
0x18015ecf9  mov     dword ptr [rsp+2A0h+var_268], r9d
0x18015ecfe  mov     dword ptr [rsp+2A0h+var_270], ecx
0x18015ed02  mov     dword ptr [rsp+2A0h+var_278], edx
0x18015ed06  mov     dword ptr [rsp+2A0h+lpOverlapped], r8d
0x18015ed0b  lea     r8, aRecordDTlsDDCo_3; "Record #%d, TLS %d.%d, Content: Handsha"...
0x18015ed12  jmp     short loc_18015ED5A
0x18015ed14  movzx   r8d, [rsp+2A0h+var_240]
0x18015ed1a  cmp     [rsp+2A0h+var_234], r15d
0x18015ed1f  movzx   ecx, [rsp+2A0h+var_235]
0x18015ed24  movzx   edx, word ptr [rsp+2A0h+var_23C]
0x18015ed29  cmovz   r10, rax
0x18015ed2d  movzx   eax, [rsp+2A0h+var_236]
0x18015ed32  movzx   r9d, [rsp+2A0h+var_23F]
0x18015ed38  mov     [rsp+2A0h+var_258], r10
0x18015ed3d  mov     dword ptr [rsp+2A0h+var_260], eax
0x18015ed41  mov     dword ptr [rsp+2A0h+var_268], ecx
0x18015ed45  mov     dword ptr [rsp+2A0h+var_270], edx
0x18015ed49  mov     dword ptr [rsp+2A0h+var_278], r8d
0x18015ed4e  lea     r8, aRecordDTlsDDCo_1; "Record #%d, TLS %d.%d, Content: Alert, "...
0x18015ed55  mov     dword ptr [rsp+2A0h+lpOverlapped], r9d
0x18015ed5a  mov     r9d, ebx
0x18015ed5d  lea     rcx, [rsp+2A0h+Buffer]; char *
0x18015ed62  mov     ebx, 1F4h
0x18015ed67  mov     edx, ebx; unsigned __int64
0x18015ed69  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x18015ed6e  jmp     short loc_18015EDB5
0x18015ed70  movzx   edx, [rsp+2A0h+var_23F]
0x18015ed75  lea     r8, aRecordDTlsDDCo_4; "Record #%d, TLS %d.%d, Content: ChangeC"...
0x18015ed7c  mov     r9d, ebx
0x18015ed7f  mov     ebx, 1F4h
0x18015ed84  movzx   ecx, [rsp+2A0h+var_240]
0x18015ed89  cmp     [rsp+2A0h+var_234], r15d
0x18015ed8e  cmovz   r10, rax
0x18015ed92  movzx   eax, word ptr [rsp+2A0h+var_23C]
0x18015ed97  mov     [rsp+2A0h+var_268], r10
0x18015ed9c  mov     dword ptr [rsp+2A0h+var_270], eax
0x18015eda0  mov     dword ptr [rsp+2A0h+var_278], ecx
0x18015eda4  lea     rcx, [rsp+2A0h+Buffer]; char *
0x18015eda9  mov     dword ptr [rsp+2A0h+lpOverlapped], edx
0x18015edad  mov     rdx, rbx; unsigned __int64
0x18015edb0  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x18015edb5  mov     rdx, rbx
0x18015edb8  lea     rax, [rsp+2A0h+Buffer]
0x18015edbd  cmp     [rax], r15b
0x18015edc0  jz      short loc_18015EDCB
0x18015edc2  inc     rax
0x18015edc5  sub     rdx, 1
0x18015edc9  jnz     short loc_18015EDBD
0x18015edcb  sub     rbx, rdx
0x18015edce  mov     [rsp+2A0h+lpOverlapped], r15; lpOverlapped
0x18015edd3  mov     rax, rdx
0x18015edd6  neg     rax
0x18015edd9  sbb     rcx, rcx
0x18015eddc  and     rcx, rbx
0x18015eddf  neg     rdx
0x18015ede2  lea     rdx, [rsp+2A0h+Buffer]; lpBuffer
0x18015ede7  sbb     r8, r8
0x18015edea  xor     r9d, r9d; lpNumberOfBytesWritten
0x18015eded  and     r8, rcx
0x18015edf0  mov     rcx, rdi; hFile
0x18015edf3  inc     r8d; nNumberOfBytesToWrite
0x18015edf6  call    cs:__imp_WriteFile
0x18015edfc  mov     ebx, r15d
0x18015edff  cmp     [rbp+1A0h+arg_20], r15d
0x18015ee06  jbe     short loc_18015EE6E
0x18015ee08  test    ebx, ebx
0x18015ee0a  jz      short loc_18015EE2D
0x18015ee0c  test    bl, 3Fh
0x18015ee0f  jnz     short loc_18015EE2D
0x18015ee11  xor     r9d, r9d; lpNumberOfBytesWritten
0x18015ee14  mov     [rsp+2A0h+lpOverlapped], r15; lpOverlapped
0x18015ee19  lea     rdx, asc_1801A6D74; "\r\n"
0x18015ee20  mov     rcx, rdi; hFile
0x18015ee23  lea     r8d, [r9+3]; nNumberOfBytesToWrite
0x18015ee27  call    cs:__imp_WriteFile
0x18015ee2d  mov     eax, ebx
0x18015ee2f  lea     r8, a02x; "%02X "
0x18015ee36  mov     edx, 3; unsigned __int64
0x18015ee3b  lea     rcx, [rsp+2A0h+var_23C]; char *
0x18015ee40  movzx   r9d, byte ptr [rax+r14]
0x18015ee45  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x18015ee4a  xor     r9d, r9d; lpNumberOfBytesWritten
0x18015ee4d  mov     [rsp+2A0h+lpOverlapped], r15; lpOverlapped
0x18015ee52  lea     rdx, [rsp+2A0h+var_23C]; lpBuffer
0x18015ee57  mov     rcx, rdi; hFile
0x18015ee5a  lea     r8d, [r9+3]; nNumberOfBytesToWrite
0x18015ee5e  call    cs:__imp_WriteFile
0x18015ee64  inc     ebx
0x18015ee66  cmp     ebx, [rbp+1A0h+arg_20]
0x18015ee6c  jb      short loc_18015EE08
0x18015ee6e  xor     r9d, r9d; lpNumberOfBytesWritten
0x18015ee71  mov     [rsp+2A0h+lpOverlapped], r15; lpOverlapped
0x18015ee76  lea     rdx, asc_1801A6DD4; "\r\n\r\n"
0x18015ee7d  mov     rcx, rdi; hFile
0x18015ee80  lea     r8d, [r9+5]; nNumberOfBytesToWrite
0x18015ee84  call    cs:__imp_WriteFile
0x18015ee8a  mov     rcx, [rbp+1A0h+var_30]
0x18015ee91  xor     rcx, rsp; StackCookie
0x18015ee94  call    __security_check_cookie
0x18015ee99  add     rsp, 280h
0x18015eea0  pop     r15
0x18015eea2  pop     r14
0x18015eea4  pop     rdi
0x18015eea5  pop     rbx
0x18015eea6  pop     rbp
0x18015eea7  retn
```
