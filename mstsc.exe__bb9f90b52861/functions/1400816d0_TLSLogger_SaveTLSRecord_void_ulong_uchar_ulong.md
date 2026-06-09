# TLSLogger::SaveTLSRecord(void *,ulong,uchar *,ulong)

- ea: `0x1400816d0`
- end: `0x140081a08`
- name: `?SaveTLSRecord@TLSLogger@@AEAAXPEAXKPEAEK@Z`
- size: `824`
- prototype: `void(TLSLogger *__hidden this, void *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140081560`

## callees

- `0x140042474`
- `0x140081484`
- `0x1400816d0`
- `0x140081ab8`
- `0x140113390`

## import_xrefs

- `KERNEL32!WriteFile` at `0x140081956`
- `KERNEL32!WriteFile` at `0x140081987`
- `KERNEL32!WriteFile` at `0x1400819be`
- `KERNEL32!WriteFile` at `0x1400819e4`
- `KERNEL32!WriteFile` at `0x140081956`
- `KERNEL32!WriteFile` at `0x140081987`
- `KERNEL32!WriteFile` at `0x1400819be`
- `KERNEL32!WriteFile` at `0x1400819e4`

## string_xrefs

- `0x14008181c`: `Record #%d, TLS %d.%d, Content: Application, Size: %d, Corrupt or incomplete: %s\n`
- `0x1400818d5`: `Record #%d, TLS %d.%d, Content: ChangeCipherSpec, Size: %d, Corrupt or incomplete: %s\n`
- `0x14008186b`: `Record #%d, TLS %d.%d, Content: Handshake, Size: %d, Handshake message type: %d (%s), Corrupt or incomplete: %s\n`
- `0x140081810`: `Record #%d, TLS %d.%d, Content: Heartbeat, Size: %d, Corrupt or incomplete: %s\n`
- `0x1400818ae`: `Record #%d, TLS %d.%d, Content: Alert, Size: %d, AlertLevel: %d, AlertCode: %d, Corrupt or incomplete: %s\n`
- `0x1400817f0`: `Record #%d, TLS %d.%d, Content: Unknown(%d), Size: %d, Corrupt or incomplete: %s\n`

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
      StringCchPrintfA(Buffer, 0x1F4u, v16, a3, lpOverlapped, v21, v22, v23, v24, v25);
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
    StringCchPrintfA(
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
  StringCchPrintfA(Buffer, 0x1F4u, v12, v10, lpOverlapped, v21, v22, v8);
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
    StringCchPrintfA(v28, 3u, "%02X ", a4[i]);
    WriteFile(a2, v28, 3u, 0, 0);
  }
  WriteFile(a2, "\r\n\r\n", 5u, 0, 0);
}

```

## disassembly

```asm
0x1400816d0  push    rbp
0x1400816d2  push    rbx
0x1400816d3  push    rdi
0x1400816d4  push    r14
0x1400816d6  push    r15
0x1400816d8  lea     rbp, [rsp-180h]
0x1400816e0  sub     rsp, 280h
0x1400816e7  mov     rax, cs:__security_cookie
0x1400816ee  xor     rax, rsp
0x1400816f1  mov     [rbp+1A0h+var_30], rax
0x1400816f8  xor     r15d, r15d
0x1400816fb  mov     [rsp+2A0h+var_234], 1
0x140081703  mov     r14, r9
0x140081706  mov     [rsp+2A0h+var_238], r15b
0x14008170b  lea     rax, [rsp+2A0h+var_234]
0x140081710  mov     [rsp+2A0h+var_23F], r15b
0x140081715  mov     [rsp+2A0h+var_250], rax; int *
0x14008171a  lea     r9, [rsp+2A0h+var_238]; unsigned __int8 *
0x14008171f  lea     rax, [rsp+2A0h+var_236]
0x140081724  mov     [rsp+2A0h+var_240], r15b
0x140081729  mov     [rsp+2A0h+var_258], rax; unsigned __int8 *
0x14008172e  mov     rdi, rdx
0x140081731  lea     rax, [rsp+2A0h+var_235]
0x140081736  mov     word ptr [rsp+2A0h+var_23C], r15w
0x14008173c  mov     [rsp+2A0h+var_260], rax; unsigned __int8 *
0x140081741  mov     ebx, r8d
0x140081744  mov     r8d, [rbp+1A0h+arg_20]; unsigned int
0x14008174b  lea     rax, [rsp+2A0h+var_237]
0x140081750  mov     [rsp+2A0h+var_268], rax; unsigned __int8 *
0x140081755  mov     rdx, r14; unsigned __int8 *
0x140081758  lea     rax, [rsp+2A0h+var_23C]
0x14008175d  mov     [rsp+2A0h+var_237], r15b
0x140081762  mov     [rsp+2A0h+var_270], rax; unsigned __int16 *
0x140081767  lea     rax, [rsp+2A0h+var_240]
0x14008176c  mov     [rsp+2A0h+var_278], rax; unsigned __int8 *
0x140081771  lea     rax, [rsp+2A0h+var_23F]
0x140081776  mov     [rsp+2A0h+lpOverlapped], rax; unsigned __int8 *
0x14008177b  mov     [rsp+2A0h+var_235], r15b
0x140081780  mov     [rsp+2A0h+var_236], r15b
0x140081785  call    ?ParseTLSRecord@TLSLogger@@AEAAXPEAEK000PEAG000PEAH@Z; TLSLogger::ParseTLSRecord(uchar *,ulong,uchar *,uchar *,uchar *,ushort *,uchar *,uchar *,uchar *,int *)
0x14008178a  movzx   r8d, [rsp+2A0h+var_238]
0x140081790  lea     r10, aYes; "YES"
0x140081797  mov     ecx, r8d
0x14008179a  lea     rax, aNo; "NO"
0x1400817a1  sub     ecx, 14h
0x1400817a4  jz      loc_1400818D0
0x1400817aa  sub     ecx, 1
0x1400817ad  jz      loc_140081874
0x1400817b3  sub     ecx, 1
0x1400817b6  jz      short loc_140081828
0x1400817b8  movzx   edx, [rsp+2A0h+var_23F]
0x1400817bd  mov     r9d, ebx
0x1400817c0  mov     ebx, 1F4h
0x1400817c5  sub     ecx, 1
0x1400817c8  jz      short loc_14008181C
0x1400817ca  cmp     ecx, 1
0x1400817cd  movzx   ecx, [rsp+2A0h+var_240]
0x1400817d2  jz      short loc_140081810
0x1400817d4  cmp     [rsp+2A0h+var_234], r15d
0x1400817d9  cmovz   r10, rax
0x1400817dd  movzx   eax, word ptr [rsp+2A0h+var_23C]
0x1400817e2  mov     [rsp+2A0h+var_260], r10
0x1400817e7  mov     dword ptr [rsp+2A0h+var_268], eax
0x1400817eb  mov     dword ptr [rsp+2A0h+var_270], r8d
0x1400817f0  lea     r8, aRecordDTlsDDCo; "Record #%d, TLS %d.%d, Content: Unknown"...
0x1400817f7  mov     dword ptr [rsp+2A0h+var_278], ecx
0x1400817fb  lea     rcx, [rsp+2A0h+Buffer]; char *
0x140081800  mov     dword ptr [rsp+2A0h+lpOverlapped], edx
0x140081804  mov     edx, ebx; unsigned __int64
0x140081806  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x14008180b  jmp     loc_140081915
0x140081810  lea     r8, aRecordDTlsDDCo_2; "Record #%d, TLS %d.%d, Content: Heartbe"...
0x140081817  jmp     loc_1400818E9
0x14008181c  lea     r8, aRecordDTlsDDCo_0; "Record #%d, TLS %d.%d, Content: Applica"...
0x140081823  jmp     loc_1400818E4
0x140081828  cmp     [rsp+2A0h+var_234], r15d
0x14008182d  movzx   r9d, [rsp+2A0h+var_237]
0x140081833  mov     edx, r9d
0x140081836  cmovz   r10, rax
0x14008183a  call    ?TLSHandshakeMessageTypeToString@TLSLogger@@AEAAPEBDW4TLSHandshakeMessageTypes@@@Z; TLSLogger::TLSHandshakeMessageTypeToString(TLSHandshakeMessageTypes)
0x14008183f  movzx   r8d, [rsp+2A0h+var_23F]
0x140081845  movzx   ecx, word ptr [rsp+2A0h+var_23C]
0x14008184a  movzx   edx, [rsp+2A0h+var_240]
0x14008184f  mov     [rsp+2A0h+var_258], r10
0x140081854  mov     [rsp+2A0h+var_260], rax
0x140081859  mov     dword ptr [rsp+2A0h+var_268], r9d
0x14008185e  mov     dword ptr [rsp+2A0h+var_270], ecx
0x140081862  mov     dword ptr [rsp+2A0h+var_278], edx
0x140081866  mov     dword ptr [rsp+2A0h+lpOverlapped], r8d
0x14008186b  lea     r8, aRecordDTlsDDCo_3; "Record #%d, TLS %d.%d, Content: Handsha"...
0x140081872  jmp     short loc_1400818BA
0x140081874  movzx   r8d, [rsp+2A0h+var_240]
0x14008187a  cmp     [rsp+2A0h+var_234], r15d
0x14008187f  movzx   ecx, [rsp+2A0h+var_235]
0x140081884  movzx   edx, word ptr [rsp+2A0h+var_23C]
0x140081889  cmovz   r10, rax
0x14008188d  movzx   eax, [rsp+2A0h+var_236]
0x140081892  movzx   r9d, [rsp+2A0h+var_23F]
0x140081898  mov     [rsp+2A0h+var_258], r10
0x14008189d  mov     dword ptr [rsp+2A0h+var_260], eax
0x1400818a1  mov     dword ptr [rsp+2A0h+var_268], ecx
0x1400818a5  mov     dword ptr [rsp+2A0h+var_270], edx
0x1400818a9  mov     dword ptr [rsp+2A0h+var_278], r8d
0x1400818ae  lea     r8, aRecordDTlsDDCo_1; "Record #%d, TLS %d.%d, Content: Alert, "...
0x1400818b5  mov     dword ptr [rsp+2A0h+lpOverlapped], r9d
0x1400818ba  mov     r9d, ebx
0x1400818bd  lea     rcx, [rsp+2A0h+Buffer]; char *
0x1400818c2  mov     ebx, 1F4h
0x1400818c7  mov     edx, ebx; unsigned __int64
0x1400818c9  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1400818ce  jmp     short loc_140081915
0x1400818d0  movzx   edx, [rsp+2A0h+var_23F]
0x1400818d5  lea     r8, aRecordDTlsDDCo_4; "Record #%d, TLS %d.%d, Content: ChangeC"...
0x1400818dc  mov     r9d, ebx
0x1400818df  mov     ebx, 1F4h
0x1400818e4  movzx   ecx, [rsp+2A0h+var_240]
0x1400818e9  cmp     [rsp+2A0h+var_234], r15d
0x1400818ee  cmovz   r10, rax
0x1400818f2  movzx   eax, word ptr [rsp+2A0h+var_23C]
0x1400818f7  mov     [rsp+2A0h+var_268], r10
0x1400818fc  mov     dword ptr [rsp+2A0h+var_270], eax
0x140081900  mov     dword ptr [rsp+2A0h+var_278], ecx
0x140081904  lea     rcx, [rsp+2A0h+Buffer]; char *
0x140081909  mov     dword ptr [rsp+2A0h+lpOverlapped], edx
0x14008190d  mov     rdx, rbx; unsigned __int64
0x140081910  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x140081915  mov     rdx, rbx
0x140081918  lea     rax, [rsp+2A0h+Buffer]
0x14008191d  cmp     [rax], r15b
0x140081920  jz      short loc_14008192B
0x140081922  inc     rax
0x140081925  sub     rdx, 1
0x140081929  jnz     short loc_14008191D
0x14008192b  sub     rbx, rdx
0x14008192e  mov     [rsp+2A0h+lpOverlapped], r15; lpOverlapped
0x140081933  mov     rax, rdx
0x140081936  neg     rax
0x140081939  sbb     rcx, rcx
0x14008193c  and     rcx, rbx
0x14008193f  neg     rdx
0x140081942  lea     rdx, [rsp+2A0h+Buffer]; lpBuffer
0x140081947  sbb     r8, r8
0x14008194a  xor     r9d, r9d; lpNumberOfBytesWritten
0x14008194d  and     r8, rcx
0x140081950  mov     rcx, rdi; hFile
0x140081953  inc     r8d; nNumberOfBytesToWrite
0x140081956  call    cs:__imp_WriteFile
0x14008195c  mov     ebx, r15d
0x14008195f  cmp     [rbp+1A0h+arg_20], r15d
0x140081966  jbe     short loc_1400819CE
0x140081968  test    ebx, ebx
0x14008196a  jz      short loc_14008198D
0x14008196c  test    bl, 3Fh
0x14008196f  jnz     short loc_14008198D
0x140081971  xor     r9d, r9d; lpNumberOfBytesWritten
0x140081974  mov     [rsp+2A0h+lpOverlapped], r15; lpOverlapped
0x140081979  lea     rdx, asc_14012F3D4; "\r\n"
0x140081980  mov     rcx, rdi; hFile
0x140081983  lea     r8d, [r9+3]; nNumberOfBytesToWrite
0x140081987  call    cs:__imp_WriteFile
0x14008198d  mov     eax, ebx
0x14008198f  lea     r8, a02x; "%02X "
0x140081996  mov     edx, 3; unsigned __int64
0x14008199b  lea     rcx, [rsp+2A0h+var_23C]; char *
0x1400819a0  movzx   r9d, byte ptr [rax+r14]
0x1400819a5  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1400819aa  xor     r9d, r9d; lpNumberOfBytesWritten
0x1400819ad  mov     [rsp+2A0h+lpOverlapped], r15; lpOverlapped
0x1400819b2  lea     rdx, [rsp+2A0h+var_23C]; lpBuffer
0x1400819b7  mov     rcx, rdi; hFile
0x1400819ba  lea     r8d, [r9+3]; nNumberOfBytesToWrite
0x1400819be  call    cs:__imp_WriteFile
0x1400819c4  inc     ebx
0x1400819c6  cmp     ebx, [rbp+1A0h+arg_20]
0x1400819cc  jb      short loc_140081968
0x1400819ce  xor     r9d, r9d; lpNumberOfBytesWritten
0x1400819d1  mov     [rsp+2A0h+lpOverlapped], r15; lpOverlapped
0x1400819d6  lea     rdx, asc_14012F3E0; "\r\n\r\n"
0x1400819dd  mov     rcx, rdi; hFile
0x1400819e0  lea     r8d, [r9+5]; nNumberOfBytesToWrite
0x1400819e4  call    cs:__imp_WriteFile
0x1400819ea  mov     rcx, [rbp+1A0h+var_30]
0x1400819f1  xor     rcx, rsp; StackCookie
0x1400819f4  call    __security_check_cookie
0x1400819f9  add     rsp, 280h
0x140081a00  pop     r15
0x140081a02  pop     r14
0x140081a04  pop     rdi
0x140081a05  pop     rbx
0x140081a06  pop     rbp
0x140081a07  retn
```
