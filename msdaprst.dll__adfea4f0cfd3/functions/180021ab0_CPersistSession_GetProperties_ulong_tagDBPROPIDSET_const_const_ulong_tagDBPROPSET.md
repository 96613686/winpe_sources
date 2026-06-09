# CPersistSession::GetProperties(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPSET * *)

- ea: `0x180021ab0`
- end: `0x180021be2`
- name: `?GetProperties@CPersistSession@@UEAAJKQEBUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPSET@@@Z`
- size: `306`
- prototype: `int(CPersistSession *__hidden this, unsigned int, const struct tagDBPROPIDSET *const, unsigned int *, struct tagDBPROPSET **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180016584`
- `0x180021ab0`
- `0x18002d31c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180021afe`
- `KERNEL32!GetCurrentThreadId` at `0x180021afe`
- `KERNEL32!LeaveCriticalSection` at `0x180021bb8`
- `KERNEL32!LeaveCriticalSection` at `0x180021bb8`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180021b23`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180021b23`
- `MSDART!UMSEnterCSWraper` at `0x180021ae4`
- `MSDART!UMSEnterCSWraper` at `0x180021ae4`

## pseudocode

```c
__int64 __fastcall CPersistSession::GetProperties(
        GUID *this,
        unsigned int a2,
        const struct tagDBPROPIDSET *const a3,
        unsigned int *a4,
        struct tagDBPROPSET **a5)
{
  GUID *v9; // r14
  unsigned __int8 *v10; // rdi
  int Properties; // eax
  unsigned int v12; // r15d
  __int64 v14; // rcx

  v9 = this + 2;
  UMSEnterCSWraper(&this[2]);
  v10 = &this[2].Data4[4];
  if ( !*(_DWORD *)&this[2].Data4[4] )
    *(_DWORD *)this[2].Data4 = GetCurrentThreadId();
  ++*(_DWORD *)v10;
  ++this[3].Data1;
  SetErrorInfo(0, 0);
  this[5] = IID_ISessionProperties;
  *(_DWORD *)&this[262].Data2 = 0;
  Properties = CUtlProps::utlGetProperties(
                 (CUtlProps *)this[283].Data4,
                 a2,
                 a3,
                 a4,
                 a5,
                 (const struct CBidGenericBase *)this[282].Data4);
  v12 = Exit(Properties, 0xBB9u);
  --this[3].Data1;
  if ( (*(_DWORD *)v10)-- == 1 )
    *(_DWORD *)this[2].Data4 = -1;
  v14 = *(_QWORD *)&v9->Data1;
  --*(_DWORD *)(v14 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v14 + 8));
  return v12;
}

```

## disassembly

```asm
0x180021ab0  mov     [rsp+arg_8], rbx
0x180021ab5  mov     [rsp+arg_10], rsi
0x180021aba  mov     [rsp+arg_0], rcx
0x180021abf  push    rdi
0x180021ac0  push    r12
0x180021ac2  push    r13
0x180021ac4  push    r14
0x180021ac6  push    r15
0x180021ac8  sub     rsp, 60h
0x180021acc  mov     r15, r9
0x180021acf  mov     r12, r8
0x180021ad2  mov     r13d, edx
0x180021ad5  mov     rbx, rcx
0x180021ad8  lea     r14, [rcx+20h]
0x180021adc  mov     [rsp+88h+var_50], r14
0x180021ae1  mov     rcx, r14
0x180021ae4  call    cs:__imp_UMSEnterCSWraper
0x180021aeb  nop     dword ptr [rax+rax+00h]
0x180021af0  lea     rdi, [rbx+2Ch]
0x180021af4  mov     [rsp+88h+var_48], rdi
0x180021af9  cmp     dword ptr [rdi], 0
0x180021afc  jnz     short loc_180021B0D
0x180021afe  call    cs:__imp_GetCurrentThreadId
0x180021b05  nop     dword ptr [rax+rax+00h]
0x180021b0a  mov     [rbx+28h], eax
0x180021b0d  inc     dword ptr [rdi]
0x180021b0f  lea     rsi, [rbx+30h]
0x180021b13  mov     [rsp+88h+var_40], rsi
0x180021b18  inc     dword ptr [rsi]
0x180021b1a  mov     [rsp+88h+var_38], r14
0x180021b1f  xor     edx, edx; perrinfo
0x180021b21  xor     ecx, ecx; dwReserved
0x180021b23  call    cs:__imp_SetErrorInfo
0x180021b2a  nop     dword ptr [rax+rax+00h]
0x180021b2f  movups  xmm0, xmmword ptr cs:IID_ISessionProperties.Data1
0x180021b36  movdqu  xmmword ptr [rbx+50h], xmm0
0x180021b3b  mov     dword ptr [rbx+1064h], 0
0x180021b45  lea     rax, [rbx+11A8h]
0x180021b4c  lea     rcx, [rbx+11B8h]; this
0x180021b53  mov     [rsp+88h+var_60], rax; struct CBidGenericBase *
0x180021b58  mov     rax, [rsp+88h+arg_20]
0x180021b60  mov     [rsp+88h+var_68], rax; struct tagDBPROPSET **
0x180021b65  mov     r9, r15; unsigned int *
0x180021b68  mov     r8, r12; struct tagDBPROPIDSET *
0x180021b6b  mov     edx, r13d; unsigned int
0x180021b6e  call    ?utlGetProperties@CUtlProps@@QEAAJKQEBUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPSET@@AEBVCBidGenericBase@@@Z; CUtlProps::utlGetProperties(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPSET * *,CBidGenericBase const &)
0x180021b73  nop
0x180021b74  jmp     short loc_180021B93
0x180021b76  jmp     short $+2
0x180021b78  mov     rsi, [rsp+88h+var_40]
0x180021b7d  mov     rdi, [rsp+88h+var_48]
0x180021b82  mov     r14, [rsp+88h+var_50]
0x180021b87  mov     eax, [rsp+88h+var_58]
0x180021b8b  mov     rbx, [rsp+88h+arg_0]
0x180021b93  mov     edx, 0BB9h; unsigned int
0x180021b98  mov     ecx, eax; int
0x180021b9a  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180021b9f  mov     r15d, eax
0x180021ba2  or      eax, 0FFFFFFFFh
0x180021ba5  add     [rsi], eax
0x180021ba7  add     [rdi], eax
0x180021ba9  jnz     short loc_180021BAE
0x180021bab  mov     [rbx+28h], eax
0x180021bae  mov     rcx, [r14]
0x180021bb1  dec     dword ptr [rcx+30h]
0x180021bb4  add     rcx, 8; lpCriticalSection
0x180021bb8  call    cs:__imp_LeaveCriticalSection
0x180021bbf  nop     dword ptr [rax+rax+00h]
0x180021bc4  mov     eax, r15d
0x180021bc7  lea     r11, [rsp+88h+var_28]
0x180021bcc  mov     rbx, [r11+38h]
0x180021bd0  mov     rsi, [r11+40h]
0x180021bd4  mov     rsp, r11
0x180021bd7  pop     r15
0x180021bd9  pop     r14
0x180021bdb  pop     r13
0x180021bdd  pop     r12
0x180021bdf  pop     rdi
0x180021be0  retn
```
