# TLSLogger::SaveTLSRecord(void *,ulong,uchar *,ulong)

- ea: `0x14007f560`
- end: `0x14007f898`
- name: `?SaveTLSRecord@TLSLogger@@AEAAXPEAXKPEAEK@Z`
- size: `824`
- prototype: `void(TLSLogger *__hidden this, void *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14007f3f0`

## callees

- `0x1400404b0`
- `0x14007f314`
- `0x14007f560`
- `0x14007f948`
- `0x140111220`

## import_xrefs

- `KERNEL32!WriteFile` at `0x14007f7e6`
- `KERNEL32!WriteFile` at `0x14007f817`
- `KERNEL32!WriteFile` at `0x14007f84e`
- `KERNEL32!WriteFile` at `0x14007f874`
- `KERNEL32!WriteFile` at `0x14007f7e6`
- `KERNEL32!WriteFile` at `0x14007f817`
- `KERNEL32!WriteFile` at `0x14007f84e`
- `KERNEL32!WriteFile` at `0x14007f874`

## string_xrefs

- `0x14007f6ac`: `Record #%d, TLS %d.%d, Content: Application, Size: %d, Corrupt or incomplete: %s\n`
- `0x14007f765`: `Record #%d, TLS %d.%d, Content: ChangeCipherSpec, Size: %d, Corrupt or incomplete: %s\n`
- `0x14007f6fb`: `Record #%d, TLS %d.%d, Content: Handshake, Size: %d, Handshake message type: %d (%s), Corrupt or incomplete: %s\n`
- `0x14007f6a0`: `Record #%d, TLS %d.%d, Content: Heartbeat, Size: %d, Corrupt or incomplete: %s\n`
- `0x14007f73e`: `Record #%d, TLS %d.%d, Content: Alert, Size: %d, AlertLevel: %d, AlertCode: %d, Corrupt or incomplete: %s\n`
- `0x14007f680`: `Record #%d, TLS %d.%d, Content: Unknown(%d), Size: %d, Corrupt or incomplete: %s\n`

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
0x14007f560  push    rbp
0x14007f562  push    rbx
0x14007f563  push    rdi
0x14007f564  push    r14
0x14007f566  push    r15
0x14007f568  lea     rbp, [rsp-180h]
0x14007f570  sub     rsp, 280h
0x14007f577  mov     rax, cs:__security_cookie
0x14007f57e  xor     rax, rsp
0x14007f581  mov     [rbp+1A0h+var_30], rax
0x14007f588  xor     r15d, r15d
0x14007f58b  mov     [rsp+2A0h+var_234], 1
0x14007f593  mov     r14, r9
0x14007f596  mov     [rsp+2A0h+var_238], r15b
0x14007f59b  lea     rax, [rsp+2A0h+var_234]
0x14007f5a0  mov     [rsp+2A0h+var_23F], r15b
0x14007f5a5  mov     [rsp+2A0h+var_250], rax; int *
0x14007f5aa  lea     r9, [rsp+2A0h+var_238]; unsigned __int8 *
0x14007f5af  lea     rax, [rsp+2A0h+var_236]
0x14007f5b4  mov     [rsp+2A0h+var_240], r15b
0x14007f5b9  mov     [rsp+2A0h+var_258], rax; unsigned __int8 *
0x14007f5be  mov     rdi, rdx
0x14007f5c1  lea     rax, [rsp+2A0h+var_235]
0x14007f5c6  mov     word ptr [rsp+2A0h+var_23C], r15w
0x14007f5cc  mov     [rsp+2A0h+var_260], rax; unsigned __int8 *
0x14007f5d1  mov     ebx, r8d
0x14007f5d4  mov     r8d, [rbp+1A0h+arg_20]; unsigned int
0x14007f5db  lea     rax, [rsp+2A0h+var_237]
0x14007f5e0  mov     [rsp+2A0h+var_268], rax; unsigned __int8 *
0x14007f5e5  mov     rdx, r14; unsigned __int8 *
0x14007f5e8  lea     rax, [rsp+2A0h+var_23C]
0x14007f5ed  mov     [rsp+2A0h+var_237], r15b
0x14007f5f2  mov     [rsp+2A0h+var_270], rax; unsigned __int16 *
0x14007f5f7  lea     rax, [rsp+2A0h+var_240]
0x14007f5fc  mov     [rsp+2A0h+var_278], rax; unsigned __int8 *
0x14007f601  lea     rax, [rsp+2A0h+var_23F]
0x14007f606  mov     [rsp+2A0h+lpOverlapped], rax; unsigned __int8 *
0x14007f60b  mov     [rsp+2A0h+var_235], r15b
0x14007f610  mov     [rsp+2A0h+var_236], r15b
0x14007f615  call    ?ParseTLSRecord@TLSLogger@@AEAAXPEAEK000PEAG000PEAH@Z; TLSLogger::ParseTLSRecord(uchar *,ulong,uchar *,uchar *,uchar *,ushort *,uchar *,uchar *,uchar *,int *)
0x14007f61a  movzx   r8d, [rsp+2A0h+var_238]
0x14007f620  lea     r10, aYes; "YES"
0x14007f627  mov     ecx, r8d
0x14007f62a  lea     rax, aNo; "NO"
0x14007f631  sub     ecx, 14h
0x14007f634  jz      loc_14007F760
0x14007f63a  sub     ecx, 1
0x14007f63d  jz      loc_14007F704
0x14007f643  sub     ecx, 1
0x14007f646  jz      short loc_14007F6B8
0x14007f648  movzx   edx, [rsp+2A0h+var_23F]
0x14007f64d  mov     r9d, ebx
0x14007f650  mov     ebx, 1F4h
0x14007f655  sub     ecx, 1
0x14007f658  jz      short loc_14007F6AC
0x14007f65a  cmp     ecx, 1
0x14007f65d  movzx   ecx, [rsp+2A0h+var_240]
0x14007f662  jz      short loc_14007F6A0
0x14007f664  cmp     [rsp+2A0h+var_234], r15d
0x14007f669  cmovz   r10, rax
0x14007f66d  movzx   eax, word ptr [rsp+2A0h+var_23C]
0x14007f672  mov     [rsp+2A0h+var_260], r10
0x14007f677  mov     dword ptr [rsp+2A0h+var_268], eax
0x14007f67b  mov     dword ptr [rsp+2A0h+var_270], r8d
0x14007f680  lea     r8, aRecordDTlsDDCo; "Record #%d, TLS %d.%d, Content: Unknown"...
0x14007f687  mov     dword ptr [rsp+2A0h+var_278], ecx
0x14007f68b  lea     rcx, [rsp+2A0h+Buffer]; char *
0x14007f690  mov     dword ptr [rsp+2A0h+lpOverlapped], edx
0x14007f694  mov     edx, ebx; unsigned __int64
0x14007f696  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x14007f69b  jmp     loc_14007F7A5
0x14007f6a0  lea     r8, aRecordDTlsDDCo_2; "Record #%d, TLS %d.%d, Content: Heartbe"...
0x14007f6a7  jmp     loc_14007F779
0x14007f6ac  lea     r8, aRecordDTlsDDCo_0; "Record #%d, TLS %d.%d, Content: Applica"...
0x14007f6b3  jmp     loc_14007F774
0x14007f6b8  cmp     [rsp+2A0h+var_234], r15d
0x14007f6bd  movzx   r9d, [rsp+2A0h+var_237]
0x14007f6c3  mov     edx, r9d
0x14007f6c6  cmovz   r10, rax
0x14007f6ca  call    ?TLSHandshakeMessageTypeToString@TLSLogger@@AEAAPEBDW4TLSHandshakeMessageTypes@@@Z; TLSLogger::TLSHandshakeMessageTypeToString(TLSHandshakeMessageTypes)
0x14007f6cf  movzx   r8d, [rsp+2A0h+var_23F]
0x14007f6d5  movzx   ecx, word ptr [rsp+2A0h+var_23C]
0x14007f6da  movzx   edx, [rsp+2A0h+var_240]
0x14007f6df  mov     [rsp+2A0h+var_258], r10
0x14007f6e4  mov     [rsp+2A0h+var_260], rax
0x14007f6e9  mov     dword ptr [rsp+2A0h+var_268], r9d
0x14007f6ee  mov     dword ptr [rsp+2A0h+var_270], ecx
0x14007f6f2  mov     dword ptr [rsp+2A0h+var_278], edx
0x14007f6f6  mov     dword ptr [rsp+2A0h+lpOverlapped], r8d
0x14007f6fb  lea     r8, aRecordDTlsDDCo_3; "Record #%d, TLS %d.%d, Content: Handsha"...
0x14007f702  jmp     short loc_14007F74A
0x14007f704  movzx   r8d, [rsp+2A0h+var_240]
0x14007f70a  cmp     [rsp+2A0h+var_234], r15d
0x14007f70f  movzx   ecx, [rsp+2A0h+var_235]
0x14007f714  movzx   edx, word ptr [rsp+2A0h+var_23C]
0x14007f719  cmovz   r10, rax
0x14007f71d  movzx   eax, [rsp+2A0h+var_236]
0x14007f722  movzx   r9d, [rsp+2A0h+var_23F]
0x14007f728  mov     [rsp+2A0h+var_258], r10
0x14007f72d  mov     dword ptr [rsp+2A0h+var_260], eax
0x14007f731  mov     dword ptr [rsp+2A0h+var_268], ecx
0x14007f735  mov     dword ptr [rsp+2A0h+var_270], edx
0x14007f739  mov     dword ptr [rsp+2A0h+var_278], r8d
0x14007f73e  lea     r8, aRecordDTlsDDCo_1; "Record #%d, TLS %d.%d, Content: Alert, "...
0x14007f745  mov     dword ptr [rsp+2A0h+lpOverlapped], r9d
0x14007f74a  mov     r9d, ebx
0x14007f74d  lea     rcx, [rsp+2A0h+Buffer]; char *
0x14007f752  mov     ebx, 1F4h
0x14007f757  mov     edx, ebx; unsigned __int64
0x14007f759  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x14007f75e  jmp     short loc_14007F7A5
0x14007f760  movzx   edx, [rsp+2A0h+var_23F]
0x14007f765  lea     r8, aRecordDTlsDDCo_4; "Record #%d, TLS %d.%d, Content: ChangeC"...
0x14007f76c  mov     r9d, ebx
0x14007f76f  mov     ebx, 1F4h
0x14007f774  movzx   ecx, [rsp+2A0h+var_240]
0x14007f779  cmp     [rsp+2A0h+var_234], r15d
0x14007f77e  cmovz   r10, rax
0x14007f782  movzx   eax, word ptr [rsp+2A0h+var_23C]
0x14007f787  mov     [rsp+2A0h+var_268], r10
0x14007f78c  mov     dword ptr [rsp+2A0h+var_270], eax
0x14007f790  mov     dword ptr [rsp+2A0h+var_278], ecx
0x14007f794  lea     rcx, [rsp+2A0h+Buffer]; char *
0x14007f799  mov     dword ptr [rsp+2A0h+lpOverlapped], edx
0x14007f79d  mov     rdx, rbx; unsigned __int64
0x14007f7a0  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x14007f7a5  mov     rdx, rbx
0x14007f7a8  lea     rax, [rsp+2A0h+Buffer]
0x14007f7ad  cmp     [rax], r15b
0x14007f7b0  jz      short loc_14007F7BB
0x14007f7b2  inc     rax
0x14007f7b5  sub     rdx, 1
0x14007f7b9  jnz     short loc_14007F7AD
0x14007f7bb  sub     rbx, rdx
0x14007f7be  mov     [rsp+2A0h+lpOverlapped], r15; lpOverlapped
0x14007f7c3  mov     rax, rdx
0x14007f7c6  neg     rax
0x14007f7c9  sbb     rcx, rcx
0x14007f7cc  and     rcx, rbx
0x14007f7cf  neg     rdx
0x14007f7d2  lea     rdx, [rsp+2A0h+Buffer]; lpBuffer
0x14007f7d7  sbb     r8, r8
0x14007f7da  xor     r9d, r9d; lpNumberOfBytesWritten
0x14007f7dd  and     r8, rcx
0x14007f7e0  mov     rcx, rdi; hFile
0x14007f7e3  inc     r8d; nNumberOfBytesToWrite
0x14007f7e6  call    cs:__imp_WriteFile
0x14007f7ec  mov     ebx, r15d
0x14007f7ef  cmp     [rbp+1A0h+arg_20], r15d
0x14007f7f6  jbe     short loc_14007F85E
0x14007f7f8  test    ebx, ebx
0x14007f7fa  jz      short loc_14007F81D
0x14007f7fc  test    bl, 3Fh
0x14007f7ff  jnz     short loc_14007F81D
0x14007f801  xor     r9d, r9d; lpNumberOfBytesWritten
0x14007f804  mov     [rsp+2A0h+lpOverlapped], r15; lpOverlapped
0x14007f809  lea     rdx, asc_14012D3D4; "\r\n"
0x14007f810  mov     rcx, rdi; hFile
0x14007f813  lea     r8d, [r9+3]; nNumberOfBytesToWrite
0x14007f817  call    cs:__imp_WriteFile
0x14007f81d  mov     eax, ebx
0x14007f81f  lea     r8, a02x; "%02X "
0x14007f826  mov     edx, 3; unsigned __int64
0x14007f82b  lea     rcx, [rsp+2A0h+var_23C]; char *
0x14007f830  movzx   r9d, byte ptr [rax+r14]
0x14007f835  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x14007f83a  xor     r9d, r9d; lpNumberOfBytesWritten
0x14007f83d  mov     [rsp+2A0h+lpOverlapped], r15; lpOverlapped
0x14007f842  lea     rdx, [rsp+2A0h+var_23C]; lpBuffer
0x14007f847  mov     rcx, rdi; hFile
0x14007f84a  lea     r8d, [r9+3]; nNumberOfBytesToWrite
0x14007f84e  call    cs:__imp_WriteFile
0x14007f854  inc     ebx
0x14007f856  cmp     ebx, [rbp+1A0h+arg_20]
0x14007f85c  jb      short loc_14007F7F8
0x14007f85e  xor     r9d, r9d; lpNumberOfBytesWritten
0x14007f861  mov     [rsp+2A0h+lpOverlapped], r15; lpOverlapped
0x14007f866  lea     rdx, asc_14012D3E0; "\r\n\r\n"
0x14007f86d  mov     rcx, rdi; hFile
0x14007f870  lea     r8d, [r9+5]; nNumberOfBytesToWrite
0x14007f874  call    cs:__imp_WriteFile
0x14007f87a  mov     rcx, [rbp+1A0h+var_30]
0x14007f881  xor     rcx, rsp; StackCookie
0x14007f884  call    __security_check_cookie
0x14007f889  add     rsp, 280h
0x14007f890  pop     r15
0x14007f892  pop     r14
0x14007f894  pop     rdi
0x14007f895  pop     rbx
0x14007f896  pop     rbp
0x14007f897  retn
```
