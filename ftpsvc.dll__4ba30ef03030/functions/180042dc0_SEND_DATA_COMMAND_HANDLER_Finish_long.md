# SEND_DATA_COMMAND_HANDLER::Finish(long)

- ea: `0x180042dc0`
- end: `0x180042f78`
- name: `?Finish@SEND_DATA_COMMAND_HANDLER@@AEAAXJ@Z`
- size: `440`
- prototype: `void __fastcall(SEND_DATA_COMMAND_HANDLER *this, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180042f80`

## callees

- `0x18003e980`
- `0x18003f9b4`
- `0x180042dc0`
- `0x18004700f`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `iisutil!?ReadLock@CSpinLock@@QEAAXXZ` at `0x180042ea1`
- `iisutil!?ReadLock@CSpinLock@@QEAAXXZ` at `0x180042ea1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180042ecd`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180042f25`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180042ecd`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180042f25`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180042e7c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180042e7c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180042f4f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180042f4f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SEND_DATA_COMMAND_HANDLER::Finish(SEND_DATA_COMMAND_HANDLER *this, int a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rbx
  int v7; // ebp
  int v8; // esi
  __int64 v9; // rax
  __int64 v10; // rbx
  const unsigned __int16 *v11; // rdx
  _BYTE v12[32]; // [rsp+30h] [rbp-E8h] BYREF
  const unsigned __int16 *v13; // [rsp+50h] [rbp-C8h]
  int v14; // [rsp+60h] [rbp-B8h]
  unsigned __int16 v15[64]; // [rsp+70h] [rbp-A8h] BYREF

  (*(void (__fastcall **)(SEND_DATA_COMMAND_HANDLER *))(*(_QWORD *)this + 40LL))(this);
  v4 = *((_QWORD *)this + 2);
  if ( a2 < 0 )
  {
    *(_DWORD *)(v4 + 4808) = 0;
    *(_QWORD *)(v4 + 4800) = 0;
    FTP_DATA_CHANNEL::InitiateChannelShutdown(
      *((FTP_DATA_CHANNEL **)this + 3),
      a2,
      *(_DWORD *)(*((_QWORD *)this + 1) + 1096LL),
      *(const unsigned __int16 **)(*((_QWORD *)this + 1) + 1104LL),
      0);
    if ( !*((_DWORD *)this + 14) )
    {
      memset_0(v15, 0, sizeof(v15));
      STRU::STRU((STRU *)v12, v15, 0x40u);
      v5 = *((_QWORD *)this + 1);
      if ( !*(_DWORD *)(v5 + 1168) )
        *(_DWORD *)(v5 + 1168) = a2;
      v6 = *((_QWORD *)this + 3);
      CSpinLock::ReadLock((CSpinLock *)(v6 + 2144));
      v7 = *(_DWORD *)(v6 + 2400);
      v8 = *(_DWORD *)(v6 + 2404);
      *v13 = 0;
      v14 = 0;
      STRU::Copy((STRU *)v12, *(const unsigned __int16 **)(v6 + 2440));
      _InterlockedExchange(
        (volatile __int32 *)(v6 + 2144),
        ((*(_BYTE *)(v6 + 2144) - 1) & 3) != 0 ? *(_DWORD *)(v6 + 2144) - 1 : 0);
      if ( v7 < 0 && v8 )
      {
        v9 = *((_QWORD *)this + 1);
        if ( !*(_DWORD *)(v9 + 1168) )
          *(_DWORD *)(v9 + 1168) = v7;
        v10 = *((_QWORD *)this + 1);
        if ( !*(_DWORD *)(v10 + 1096) )
        {
          v11 = v13;
          *(_DWORD *)(v10 + 1096) = v8;
          STRU::Copy((STRU *)(v10 + 1112), v11);
          *(_QWORD *)(v10 + 1104) = *(_QWORD *)(v10 + 1144);
        }
      }
      FTP_COMMAND::WriteResponseWithErrorTextAndLog(*((FTP_COMMAND **)this + 1), "550");
      STRU::~STRU(v12);
    }
  }
  else
  {
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v4 + 96) + 104LL));
    (*(void (__fastcall **)(SEND_DATA_COMMAND_HANDLER *))(*(_QWORD *)this + 32LL))(this);
  }
}

```

## disassembly

```asm
0x180042dc0  mov     [rsp+arg_10], rbx
0x180042dc5  push    rbp
0x180042dc6  push    rsi
0x180042dc7  push    rdi
0x180042dc8  sub     rsp, 100h
0x180042dcf  mov     rax, cs:__security_cookie
0x180042dd6  xor     rax, rsp
0x180042dd9  mov     [rsp+118h+var_28], rax
0x180042de1  mov     ebx, edx
0x180042de3  mov     rdi, rcx
0x180042de6  mov     rax, [rcx]
0x180042de9  mov     rax, [rax+28h]
0x180042ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042df2  mov     rax, [rdi+10h]
0x180042df6  test    ebx, ebx
0x180042df8  js      short loc_180042E16
0x180042dfa  mov     rax, [rax+60h]
0x180042dfe  lock inc dword ptr [rax+68h]
0x180042e02  mov     rax, [rdi]
0x180042e05  mov     rcx, rdi
0x180042e08  mov     rax, [rax+20h]
0x180042e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042e11  jmp     loc_180042F55
0x180042e16  mov     dword ptr [rax+12C8h], 0
0x180042e20  mov     qword ptr [rax+12C0h], 0
0x180042e2b  mov     r8, [rdi+8]
0x180042e2f  mov     [rsp+118h+var_F8], 0; int
0x180042e37  mov     r9, [r8+450h]; unsigned __int16 *
0x180042e3e  mov     r8d, [r8+448h]; unsigned int
0x180042e45  mov     edx, ebx; int
0x180042e47  mov     rcx, [rdi+18h]; this
0x180042e4b  call    ?InitiateChannelShutdown@FTP_DATA_CHANNEL@@QEAAXJKPEBGH@Z; FTP_DATA_CHANNEL::InitiateChannelShutdown(long,ulong,ushort const *,int)
0x180042e50  cmp     dword ptr [rdi+38h], 0
0x180042e54  jnz     loc_180042F55
0x180042e5a  xor     edx, edx; Val
0x180042e5c  mov     r8d, 80h; Size
0x180042e62  lea     rcx, [rsp+118h+var_A8]; void *
0x180042e67  call    memset_0
0x180042e6c  mov     r8d, 40h ; '@'
0x180042e72  lea     rdx, [rsp+118h+var_A8]
0x180042e77  lea     rcx, [rsp+118h+var_E8]
0x180042e7c  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180042e82  nop
0x180042e83  mov     rax, [rdi+8]
0x180042e87  cmp     dword ptr [rax+490h], 0
0x180042e8e  jnz     short loc_180042E96
0x180042e90  mov     [rax+490h], ebx
0x180042e96  mov     rbx, [rdi+18h]
0x180042e9a  lea     rcx, [rbx+860h]
0x180042ea1  call    cs:__imp_?ReadLock@CSpinLock@@QEAAXXZ; CSpinLock::ReadLock(void)
0x180042ea7  mov     ebp, [rbx+960h]
0x180042ead  mov     esi, [rbx+964h]
0x180042eb3  xor     ecx, ecx
0x180042eb5  mov     rax, [rsp+118h+var_C8]
0x180042eba  mov     [rax], cx
0x180042ebd  mov     [rsp+118h+var_B8], ecx
0x180042ec1  mov     rdx, [rbx+988h]
0x180042ec8  lea     rcx, [rsp+118h+var_E8]
0x180042ecd  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180042ed3  mov     edx, [rbx+860h]
0x180042ed9  dec     edx
0x180042edb  mov     eax, edx
0x180042edd  and     al, 3
0x180042edf  neg     al
0x180042ee1  sbb     ecx, ecx
0x180042ee3  and     ecx, edx
0x180042ee5  xchg    ecx, [rbx+860h]
0x180042eeb  test    ebp, ebp
0x180042eed  jns     short loc_180042F39
0x180042eef  test    esi, esi
0x180042ef1  jz      short loc_180042F39
0x180042ef3  mov     rax, [rdi+8]
0x180042ef7  cmp     dword ptr [rax+490h], 0
0x180042efe  jnz     short loc_180042F06
0x180042f00  mov     [rax+490h], ebp
0x180042f06  mov     rbx, [rdi+8]
0x180042f0a  cmp     dword ptr [rbx+448h], 0
0x180042f11  jnz     short loc_180042F39
0x180042f13  mov     rdx, [rsp+118h+var_C8]
0x180042f18  mov     [rbx+448h], esi
0x180042f1e  lea     rcx, [rbx+458h]
0x180042f25  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180042f2b  mov     rax, [rbx+478h]
0x180042f32  mov     [rbx+450h], rax
0x180042f39  lea     rdx, a550; "550"
0x180042f40  mov     rcx, [rdi+8]; this
0x180042f44  call    ?WriteResponseWithErrorTextAndLog@FTP_COMMAND@@QEAAJPEBD@Z; FTP_COMMAND::WriteResponseWithErrorTextAndLog(char const *)
0x180042f49  nop
0x180042f4a  lea     rcx, [rsp+118h+var_E8]
0x180042f4f  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180042f55  mov     rcx, [rsp+118h+var_28]
0x180042f5d  xor     rcx, rsp; StackCookie
0x180042f60  call    __security_check_cookie
0x180042f65  mov     rbx, [rsp+118h+arg_10]
0x180042f6d  add     rsp, 100h
0x180042f74  pop     rdi
0x180042f75  pop     rsi
0x180042f76  pop     rbp
0x180042f77  retn
```
