# SEND_DATA_COMMAND_HANDLER::Start(int *)

- ea: `0x180043258`
- end: `0x1800434a0`
- name: `?Start@SEND_DATA_COMMAND_HANDLER@@AEAAJPEAH@Z`
- size: `584`
- prototype: `int(SEND_DATA_COMMAND_HANDLER *__hidden this, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180042f80`

## callees

- `0x1800139e4`
- `0x1800384cc`
- `0x18003e384`
- `0x18003e564`
- `0x18003fed0`
- `0x180043258`
- `0x18004700f`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `iisutil!?ReadLock@CSpinLock@@QEAAXXZ` at `0x1800433c7`
- `iisutil!?ReadLock@CSpinLock@@QEAAXXZ` at `0x1800433c7`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800433f4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004344e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800433f4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004344e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800433a2`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800433a2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180043485`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180043485`

## string_xrefs

- `0x180043462`: `Cannot open data connection.`
- `0x1800432fe`: `Data connection already open; Transfer starting.`
- `0x180043344`: `Opening %s mode data connection.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SEND_DATA_COMMAND_HANDLER::Start(FTP_COMMAND **this, int *a2)
{
  int v4; // esi
  const char *v6; // r9
  FTP_COMMAND *v7; // rax
  FTP_COMMAND *v8; // rbx
  int v9; // r14d
  int v10; // ebp
  FTP_COMMAND *v11; // rax
  FTP_COMMAND *v12; // rbx
  const unsigned __int16 *v13; // rdx
  _BYTE v14[32]; // [rsp+20h] [rbp-E8h] BYREF
  const unsigned __int16 *v15; // [rsp+40h] [rbp-C8h]
  int v16; // [rsp+50h] [rbp-B8h]
  unsigned __int16 v17[64]; // [rsp+60h] [rbp-A8h] BYREF

  v4 = FTP_COMMAND::CheckDataChannelPolicyBeforeDataTransfer(this[1]);
  if ( v4 < 0 )
  {
    *((_DWORD *)this + 14) = 1;
    return (unsigned int)v4;
  }
  v4 = (*((__int64 (__fastcall **)(FTP_COMMAND **))*this + 1))(this);
  if ( v4 < 0 )
    return (unsigned int)v4;
  v4 = DATA_STREAM_BUFFER::ResizeBuffer(this[6], 0xFFFFu, 0);
  if ( v4 < 0 )
    return (unsigned int)v4;
  if ( *((int *)this[3] + 539) < 0 )
  {
    if ( *((_DWORD *)this[2] + 1194) == 1 )
    {
      v6 = "ASCII";
    }
    else if ( *((_DWORD *)this[2] + 1194) == 2 )
    {
      v6 = "BINARY";
    }
    else
    {
      v6 = String;
    }
    FTP_COMMAND::WriteResponse(this[1], "150", "Opening %s mode data connection.", v6);
  }
  else
  {
    FTP_COMMAND::WriteResponse(this[1], "125", "Data connection already open; Transfer starting.");
  }
  *((_DWORD *)this[5] + 16) = 1;
  v4 = FTP_DATA_CHANNEL::NotifyOnNewConnectionReady(this[3], this[5], a2);
  if ( v4 < 0 )
  {
    memset_0(v17, 0, sizeof(v17));
    STRU::STRU((STRU *)v14, v17, 0x40u);
    v7 = this[1];
    if ( !*((_DWORD *)v7 + 292) )
      *((_DWORD *)v7 + 292) = v4;
    v8 = this[3];
    CSpinLock::ReadLock((FTP_COMMAND *)((char *)v8 + 2144));
    v9 = *((_DWORD *)v8 + 600);
    v10 = *((_DWORD *)v8 + 601);
    *v15 = 0;
    v16 = 0;
    STRU::Copy((STRU *)v14, *((const unsigned __int16 **)v8 + 305));
    _InterlockedExchange(
      (volatile __int32 *)v8 + 536,
      ((*((_BYTE *)v8 + 2144) - 1) & 3) != 0 ? *((_DWORD *)v8 + 536) - 1 : 0);
    if ( v9 < 0 && v10 )
    {
      v11 = this[1];
      if ( !*((_DWORD *)v11 + 292) )
        *((_DWORD *)v11 + 292) = v9;
      v12 = this[1];
      if ( !*((_DWORD *)v12 + 274) )
      {
        v13 = v15;
        *((_DWORD *)v12 + 274) = v10;
        STRU::Copy((FTP_COMMAND *)((char *)v12 + 1112), v13);
        *((_QWORD *)v12 + 138) = *((_QWORD *)v12 + 143);
      }
    }
    FTP_COMMAND::WriteResponseAndLog(this[1], "425", "Cannot open data connection.");
    *((_DWORD *)this + 14) = 1;
    STRU::~STRU(v14);
    return (unsigned int)v4;
  }
  if ( !*a2 )
    return (unsigned int)v4;
  return 0;
}

```

## disassembly

```asm
0x180043258  mov     [rsp+arg_10], rbx
0x18004325d  mov     [rsp+arg_18], rbp
0x180043262  push    rsi
0x180043263  push    rdi
0x180043264  push    r14
0x180043266  sub     rsp, 0F0h
0x18004326d  mov     rax, cs:__security_cookie
0x180043274  xor     rax, rsp
0x180043277  mov     [rsp+108h+var_28], rax
0x18004327f  mov     rbx, rdx
0x180043282  mov     rdi, rcx
0x180043285  mov     rcx, [rcx+8]; this
0x180043289  call    ?CheckDataChannelPolicyBeforeDataTransfer@FTP_COMMAND@@QEAAJXZ; FTP_COMMAND::CheckDataChannelPolicyBeforeDataTransfer(void)
0x18004328e  mov     esi, eax
0x180043290  test    eax, eax
0x180043292  jns     short loc_1800432C5
0x180043294  mov     dword ptr [rdi+38h], 1
0x18004329b  mov     eax, esi
0x18004329d  mov     rcx, [rsp+108h+var_28]
0x1800432a5  xor     rcx, rsp; StackCookie
0x1800432a8  call    __security_check_cookie
0x1800432ad  lea     r11, [rsp+108h+var_18]
0x1800432b5  mov     rbx, [r11+30h]
0x1800432b9  mov     rbp, [r11+38h]
0x1800432bd  mov     rsp, r11
0x1800432c0  pop     r14
0x1800432c2  pop     rdi
0x1800432c3  pop     rsi
0x1800432c4  retn
0x1800432c5  mov     rax, [rdi]
0x1800432c8  mov     rcx, rdi
0x1800432cb  mov     rax, [rax+8]
0x1800432cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800432d4  mov     esi, eax
0x1800432d6  test    eax, eax
0x1800432d8  js      short loc_18004329B
0x1800432da  xor     r8d, r8d; int
0x1800432dd  mov     edx, 0FFFFh; unsigned int
0x1800432e2  mov     rcx, [rdi+30h]; this
0x1800432e6  call    ?ResizeBuffer@DATA_STREAM_BUFFER@@QEAAJKH@Z; DATA_STREAM_BUFFER::ResizeBuffer(ulong,int)
0x1800432eb  mov     esi, eax
0x1800432ed  test    eax, eax
0x1800432ef  js      short loc_18004329B
0x1800432f1  mov     rax, [rdi+18h]
0x1800432f5  cmp     dword ptr [rax+86Ch], 0
0x1800432fc  jl      short loc_180043317
0x1800432fe  lea     r8, aDataConnection; "Data connection already open; Transfer "...
0x180043305  lea     rdx, a125; "125"
0x18004330c  mov     rcx, [rdi+8]; this
0x180043310  call    ?WriteResponse@FTP_COMMAND@@QEAAJPEBD0ZZ; FTP_COMMAND::WriteResponse(char const *,char const *,...)
0x180043315  jmp     short loc_18004335B
0x180043317  mov     rcx, [rdi+10h]
0x18004331b  mov     edx, [rcx+12A8h]
0x180043321  sub     edx, 1
0x180043324  jz      short loc_18004333D
0x180043326  cmp     edx, 1
0x180043329  jz      short loc_180043334
0x18004332b  lea     r9, String
0x180043332  jmp     short loc_180043344
0x180043334  lea     r9, aBinary; "BINARY"
0x18004333b  jmp     short loc_180043344
0x18004333d  lea     r9, aAscii; "ASCII"
0x180043344  lea     r8, aOpeningSModeDa; "Opening %s mode data connection."
0x18004334b  lea     rdx, a150; "150"
0x180043352  mov     rcx, [rdi+8]; this
0x180043356  call    ?WriteResponse@FTP_COMMAND@@QEAAJPEBD0ZZ; FTP_COMMAND::WriteResponse(char const *,char const *,...)
0x18004335b  mov     rax, [rdi+28h]
0x18004335f  mov     dword ptr [rax+40h], 1
0x180043366  mov     r8, rbx; int *
0x180043369  mov     rdx, [rdi+28h]; struct FTP_ASYNC_CONTEXT *
0x18004336d  mov     rcx, [rdi+18h]; this
0x180043371  call    ?NotifyOnNewConnectionReady@FTP_DATA_CHANNEL@@QEAAJPEAVFTP_ASYNC_CONTEXT@@PEAH@Z; FTP_DATA_CHANNEL::NotifyOnNewConnectionReady(FTP_ASYNC_CONTEXT *,int *)
0x180043376  mov     esi, eax
0x180043378  test    eax, eax
0x18004337a  jns     loc_180043490
0x180043380  xor     edx, edx; Val
0x180043382  mov     r8d, 80h; Size
0x180043388  lea     rcx, [rsp+108h+var_A8]; void *
0x18004338d  call    memset_0
0x180043392  mov     r8d, 40h ; '@'
0x180043398  lea     rdx, [rsp+108h+var_A8]
0x18004339d  lea     rcx, [rsp+108h+var_E8]
0x1800433a2  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800433a8  nop
0x1800433a9  mov     rax, [rdi+8]
0x1800433ad  cmp     dword ptr [rax+490h], 0
0x1800433b4  jnz     short loc_1800433BC
0x1800433b6  mov     [rax+490h], esi
0x1800433bc  mov     rbx, [rdi+18h]
0x1800433c0  lea     rcx, [rbx+860h]
0x1800433c7  call    cs:__imp_?ReadLock@CSpinLock@@QEAAXXZ; CSpinLock::ReadLock(void)
0x1800433cd  mov     r14d, [rbx+960h]
0x1800433d4  mov     ebp, [rbx+964h]
0x1800433da  xor     ecx, ecx
0x1800433dc  mov     rax, [rsp+108h+var_C8]
0x1800433e1  mov     [rax], cx
0x1800433e4  mov     [rsp+108h+var_B8], ecx
0x1800433e8  mov     rdx, [rbx+988h]
0x1800433ef  lea     rcx, [rsp+108h+var_E8]
0x1800433f4  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800433fa  mov     edx, [rbx+860h]
0x180043400  dec     edx
0x180043402  mov     eax, edx
0x180043404  and     al, 3
0x180043406  neg     al
0x180043408  sbb     ecx, ecx
0x18004340a  and     ecx, edx
0x18004340c  xchg    ecx, [rbx+860h]
0x180043412  test    r14d, r14d
0x180043415  jns     short loc_180043462
0x180043417  test    ebp, ebp
0x180043419  jz      short loc_180043462
0x18004341b  mov     rax, [rdi+8]
0x18004341f  cmp     dword ptr [rax+490h], 0
0x180043426  jnz     short loc_18004342F
0x180043428  mov     [rax+490h], r14d
0x18004342f  mov     rbx, [rdi+8]
0x180043433  cmp     dword ptr [rbx+448h], 0
0x18004343a  jnz     short loc_180043462
0x18004343c  mov     rdx, [rsp+108h+var_C8]
0x180043441  mov     [rbx+448h], ebp
0x180043447  lea     rcx, [rbx+458h]
0x18004344e  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180043454  mov     rax, [rbx+478h]
0x18004345b  mov     [rbx+450h], rax
0x180043462  lea     r8, aCannotOpenData; "Cannot open data connection."
0x180043469  lea     rdx, a425; "425"
0x180043470  mov     rcx, [rdi+8]; this
0x180043474  call    ?WriteResponseAndLog@FTP_COMMAND@@QEAAJPEBD0ZZ; FTP_COMMAND::WriteResponseAndLog(char const *,char const *,...)
0x180043479  mov     dword ptr [rdi+38h], 1
0x180043480  lea     rcx, [rsp+108h+var_E8]
0x180043485  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18004348b  jmp     loc_18004329B
0x180043490  cmp     dword ptr [rbx], 0
0x180043493  jz      loc_18004329B
0x180043499  xor     eax, eax
0x18004349b  jmp     loc_18004329D
```
