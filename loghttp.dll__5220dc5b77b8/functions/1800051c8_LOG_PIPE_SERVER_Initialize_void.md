# LOG_PIPE_SERVER::Initialize(void)

- ea: `0x1800051c8`
- end: `0x18000533f`
- name: `?Initialize@LOG_PIPE_SERVER@@QEAAJXZ`
- size: `375`
- prototype: `__int64 __fastcall(LOG_PIPE_SERVER *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800038f8`

## callees

- `0x180004d14`
- `0x1800051c8`
- `0x1800056f2`
- `0x180005720`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005302`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000530b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005302`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000530b`
- `iisutil!?DestroyIpmMessagePipe@IPM2_MESSAGE_PIPE@@QEAAXXZ` at `0x1800052d6`
- `iisutil!?DestroyIpmMessagePipe@IPM2_MESSAGE_PIPE@@QEAAXXZ` at `0x1800052d6`
- `iisutil!GenerateNameWithGUID` at `0x180005228`
- `iisutil!GenerateNameWithGUID` at `0x180005228`
- `iisutil!?CreateIpmMessagePipe@IPM2_MESSAGE_PIPE@@SAJPEAVIPM2_MESSAGE_ACCEPTOR@@PEBGHHKPEAU_SECURITY_ATTRIBUTES@@PEAPEAV1@PEAH@Z` at `0x180005296`
- `iisutil!?CreateIpmMessagePipe@IPM2_MESSAGE_PIPE@@SAJPEAVIPM2_MESSAGE_ACCEPTOR@@PEBGHHKPEAU_SECURITY_ATTRIBUTES@@PEAPEAV1@PEAH@Z` at `0x180005296`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x1800052b7`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x1800052b7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005316`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005316`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000525a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800052a7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000525a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800052a7`
- `iisutil!?Reset@STRA@@QEAAXXZ` at `0x1800052ee`
- `iisutil!?Reset@STRA@@QEAAXXZ` at `0x1800052ee`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000520f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000520f`

## pseudocode

```c
__int64 __fastcall LOG_PIPE_SERVER::Initialize(LOG_PIPE_SERVER *this)
{
  struct _SECURITY_ATTRIBUTES *v1; // rdi
  int NameWithGUID; // eax
  LOG_PIPE_SERVER *v3; // rcx
  signed int IpmMessagePipe; // ebx
  const unsigned __int16 *Str; // rax
  const unsigned __int16 *v6; // rax
  void *lpSecurityDescriptor; // rcx
  struct _SECURITY_ATTRIBUTES *v9; // [rsp+40h] [rbp-D8h] BYREF
  _BYTE v10[56]; // [rsp+48h] [rbp-D0h] BYREF
  unsigned __int16 v11[64]; // [rsp+80h] [rbp-98h] BYREF

  memset_0(v11, 0, sizeof(v11));
  STRU::STRU((STRU *)v10, v11, 0x40u);
  v1 = 0;
  v9 = 0;
  NameWithGUID = GenerateNameWithGUID(L"\\\\.\\pipe\\iislogpipe", (struct STRU *)v10);
  IpmMessagePipe = NameWithGUID;
  if ( NameWithGUID )
  {
    if ( NameWithGUID > 0 )
      IpmMessagePipe = (unsigned __int16)NameWithGUID | 0x80070000;
LABEL_7:
    if ( IpmMessagePipe >= 0 )
      goto LABEL_13;
    goto LABEL_10;
  }
  IpmMessagePipe = LOG_PIPE_SERVER::CreatePipeSecurity(v3, &v9);
  if ( IpmMessagePipe < 0 )
  {
    v1 = v9;
  }
  else
  {
    Str = STRU::QueryStr((STRU *)v10);
    v1 = v9;
    IpmMessagePipe = IPM2_MESSAGE_PIPE::CreateIpmMessagePipe(
                       (struct IPM2_MESSAGE_ACCEPTOR *)&HTTP_LOG_HANDLER::sm_logPipeServer,
                       Str,
                       1,
                       1,
                       0xFFu,
                       v9,
                       (struct IPM2_MESSAGE_PIPE **)&qword_18000B010,
                       0);
    if ( IpmMessagePipe >= 0 )
    {
      v6 = STRU::QueryStr((STRU *)v10);
      IpmMessagePipe = STRA::CopyW((STRA *)qword_18000B018, v6);
      goto LABEL_7;
    }
  }
LABEL_10:
  if ( qword_18000B010 )
  {
    IPM2_MESSAGE_PIPE::DestroyIpmMessagePipe((IPM2_MESSAGE_PIPE *)qword_18000B010);
    qword_18000B010 = 0;
  }
  STRA::Reset((STRA *)qword_18000B018);
LABEL_13:
  if ( v1 )
  {
    lpSecurityDescriptor = v1->lpSecurityDescriptor;
    if ( lpSecurityDescriptor )
      LocalFree(lpSecurityDescriptor);
    LocalFree(v1);
  }
  STRU::~STRU((STRU *)v10);
  return (unsigned int)IpmMessagePipe;
}

```

## disassembly

```asm
0x1800051c8  mov     [rsp+arg_0], rbx
0x1800051cd  push    rdi
0x1800051ce  sub     rsp, 110h
0x1800051d5  mov     rax, cs:__security_cookie
0x1800051dc  xor     rax, rsp
0x1800051df  mov     [rsp+118h+var_18], rax
0x1800051e7  xor     edx, edx; Val
0x1800051e9  lea     rcx, [rsp+118h+var_98]; void *
0x1800051f1  mov     r8d, 80h; Size
0x1800051f7  call    memset_0
0x1800051fc  mov     r8d, 40h ; '@'
0x180005202  lea     rdx, [rsp+118h+var_98]
0x18000520a  lea     rcx, [rsp+118h+var_D0]
0x18000520f  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180005215  xor     edi, edi
0x180005217  lea     rdx, [rsp+118h+var_D0]
0x18000521c  lea     rcx, aPipeIislogpipe; "\\\\.\\pipe\\iislogpipe"
0x180005223  mov     [rsp+118h+var_D8], rdi
0x180005228  call    cs:__imp_?GenerateNameWithGUID@@YAKPEBGPEAVSTRU@@@Z; GenerateNameWithGUID(ushort const *,STRU *)
0x18000522e  mov     ebx, eax
0x180005230  test    eax, eax
0x180005232  jz      short loc_180005245
0x180005234  jle     loc_1800052BF
0x18000523a  movzx   ebx, ax
0x18000523d  or      ebx, 80070000h
0x180005243  jmp     short loc_1800052BF
0x180005245  lea     rdx, [rsp+118h+var_D8]; struct _SECURITY_ATTRIBUTES **
0x18000524a  call    ?CreatePipeSecurity@LOG_PIPE_SERVER@@AEAAJPEAPEAU_SECURITY_ATTRIBUTES@@@Z; LOG_PIPE_SERVER::CreatePipeSecurity(_SECURITY_ATTRIBUTES * *)
0x18000524f  mov     ebx, eax
0x180005251  test    eax, eax
0x180005253  js      short loc_1800052C5
0x180005255  lea     rcx, [rsp+118h+var_D0]
0x18000525a  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180005260  mov     [rsp+118h+var_E0], rdi
0x180005265  lea     rcx, qword_18000B010
0x18000526c  mov     rdi, [rsp+118h+var_D8]
0x180005271  mov     r8d, 1
0x180005277  mov     [rsp+118h+var_E8], rcx
0x18000527c  mov     r9d, r8d
0x18000527f  mov     [rsp+118h+var_F0], rdi
0x180005284  lea     rcx, ?sm_logPipeServer@HTTP_LOG_HANDLER@@0VLOG_PIPE_SERVER@@A; LOG_PIPE_SERVER HTTP_LOG_HANDLER::sm_logPipeServer
0x18000528b  mov     rdx, rax
0x18000528e  mov     [rsp+118h+var_F8], 0FFh
0x180005296  call    cs:__imp_?CreateIpmMessagePipe@IPM2_MESSAGE_PIPE@@SAJPEAVIPM2_MESSAGE_ACCEPTOR@@PEBGHHKPEAU_SECURITY_ATTRIBUTES@@PEAPEAV1@PEAH@Z; IPM2_MESSAGE_PIPE::CreateIpmMessagePipe(IPM2_MESSAGE_ACCEPTOR *,ushort const *,int,int,ulong,_SECURITY_ATTRIBUTES *,IPM2_MESSAGE_PIPE * *,int *)
0x18000529c  mov     ebx, eax
0x18000529e  test    eax, eax
0x1800052a0  js      short loc_1800052CA
0x1800052a2  lea     rcx, [rsp+118h+var_D0]
0x1800052a7  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800052ad  mov     rdx, rax
0x1800052b0  lea     rcx, qword_18000B018
0x1800052b7  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x1800052bd  mov     ebx, eax
0x1800052bf  test    ebx, ebx
0x1800052c1  jns     short loc_1800052F4
0x1800052c3  jmp     short loc_1800052CA
0x1800052c5  mov     rdi, [rsp+118h+var_D8]
0x1800052ca  mov     rcx, cs:qword_18000B010
0x1800052d1  test    rcx, rcx
0x1800052d4  jz      short loc_1800052E7
0x1800052d6  call    cs:__imp_?DestroyIpmMessagePipe@IPM2_MESSAGE_PIPE@@QEAAXXZ; IPM2_MESSAGE_PIPE::DestroyIpmMessagePipe(void)
0x1800052dc  mov     cs:qword_18000B010, 0
0x1800052e7  lea     rcx, qword_18000B018
0x1800052ee  call    cs:__imp_?Reset@STRA@@QEAAXXZ; STRA::Reset(void)
0x1800052f4  test    rdi, rdi
0x1800052f7  jz      short loc_180005311
0x1800052f9  mov     rcx, [rdi+8]; hMem
0x1800052fd  test    rcx, rcx
0x180005300  jz      short loc_180005308
0x180005302  call    cs:__imp_LocalFree
0x180005308  mov     rcx, rdi; hMem
0x18000530b  call    cs:__imp_LocalFree
0x180005311  lea     rcx, [rsp+118h+var_D0]
0x180005316  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000531c  mov     eax, ebx
0x18000531e  mov     rcx, [rsp+118h+var_18]
0x180005326  xor     rcx, rsp; StackCookie
0x180005329  call    __security_check_cookie
0x18000532e  mov     rbx, [rsp+118h+arg_0]
0x180005336  add     rsp, 110h
0x18000533d  pop     rdi
0x18000533e  retn
```
