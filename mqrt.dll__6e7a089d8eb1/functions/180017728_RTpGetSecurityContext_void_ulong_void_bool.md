# RTpGetSecurityContext(void *,ulong,void * *,bool)

- ea: `0x180017728`
- end: `0x180017a66`
- name: `?RTpGetSecurityContext@@YAJPEAXKPEAPEAX_N@Z`
- size: `830`
- prototype: `__int64 __fastcall(void *, unsigned int, void **, bool)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017cc0`
- `0x180017cd0`

## callees

- `0x1800134e8`
- `0x180013c74`
- `0x180014458`
- `0x180016178`
- `0x18001620c`
- `0x1800164a8`
- `0x1800166dc`
- `0x18001753c`
- `0x1800176d4`
- `0x180017728`
- `0x180017a6c`
- `0x180021010`
- `0x180026010`

## import_xrefs

- `msvcrt!free` at `0x1800177e0`
- `msvcrt!free` at `0x180017857`
- `msvcrt!free` at `0x180017887`
- `msvcrt!free` at `0x1800178e4`
- `msvcrt!free` at `0x180017957`
- `msvcrt!free` at `0x180017987`
- `msvcrt!free` at `0x1800179d7`
- `msvcrt!free` at `0x180017a04`
- `msvcrt!free` at `0x180017a43`
- `msvcrt!free` at `0x1800177e0`
- `msvcrt!free` at `0x180017857`
- `msvcrt!free` at `0x180017887`
- `msvcrt!free` at `0x1800178e4`
- `msvcrt!free` at `0x180017957`
- `msvcrt!free` at `0x180017987`
- `msvcrt!free` at `0x1800179d7`
- `msvcrt!free` at `0x180017a04`
- `msvcrt!free` at `0x180017a43`
- `mqsec!MQSec_GetThreadUserSid` at `0x1800178b3`
- `mqsec!MQSec_GetThreadUserSid` at `0x1800178b3`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall RTpGetSecurityContext(void *a1, unsigned int a2, void **a3, char a4)
{
  int v8; // eax
  unsigned int v9; // ebx
  UserSecurityContext *v10; // rax
  CContextMap *v11; // rcx
  UserSecurityContext *v12; // rbx
  void *v13; // rsi
  int v14; // eax
  unsigned int v15; // edi
  int v16; // eax
  unsigned int v17; // edi
  int ThreadUserSid; // eax
  unsigned int v19; // edi
  int v20; // eax
  __int64 v21; // rdx
  int v22; // r15d
  int v23; // eax
  unsigned int v24; // edi
  int v25; // eax
  unsigned int v26; // ebx
  unsigned int v28; // [rsp+20h] [rbp-58h] BYREF
  UserSecurityContext *v29; // [rsp+28h] [rbp-50h] BYREF
  void *Block; // [rsp+30h] [rbp-48h] BYREF
  _QWORD v31[8]; // [rsp+38h] [rbp-40h] BYREF

  v8 = RtpOneTimeThreadInit();
  v9 = v8;
  if ( v8 < 0 )
  {
    LogMsgHR(v8, (wchar_t *)L"rt/rtctxex", 0x44Fu);
    return v9;
  }
  v10 = (UserSecurityContext *)MmAllocate(0xC8u);
  v31[0] = v10;
  if ( v10 )
    v12 = UserSecurityContext::UserSecurityContext(v10);
  else
    v12 = 0;
  v29 = v12;
  v13 = (void *)(int)CContextMap::AddContext(v11, v12);
  Block = 0;
  v31[0] = 0;
  v14 = RTSecurityContextBase::InitializeUserInfo(v12);
  v15 = v14;
  if ( v14 < 0 )
  {
    LogMsgHR(v14, (wchar_t *)L"rt/rtctxex", 0x3Cu);
    CHCryptKey::~CHCryptKey((CHCryptKey *)v31);
    free(Block);
    P<UserSecurityContext>::~P<UserSecurityContext>(&v29);
    return v15;
  }
  if ( a1 )
    RTSecurityContextBase::AllocateAndCopyUserCert(v12, a1, a2);
  if ( a4 || (v16 = (**(__int64 (__fastcall ***)(UserSecurityContext *, _QWORD))v12)(v12, 0), v17 = v16, v16 >= 0) )
  {
    v28 = 0;
    ThreadUserSid = MQSec_GetThreadUserSid(0, &Block, &v28, 0);
    v19 = ThreadUserSid;
    if ( ThreadUserSid < 0 )
    {
      LogMsgHR(ThreadUserSid, (wchar_t *)L"rt/rtctxex", 0x5Au);
      CHCryptKey::~CHCryptKey((CHCryptKey *)v31);
      free(Block);
      P<UserSecurityContext>::~P<UserSecurityContext>(&v29);
      return v19;
    }
    v20 = SameAsProcessSid(Block);
    v22 = v20;
    if ( a4
      && (LOBYTE(v21) = v20 == 0,
          v23 = (**(__int64 (__fastcall ***)(UserSecurityContext *, __int64))v12)(v12, v21),
          v24 = v23,
          v23 < 0) )
    {
      if ( v23 != -1072824273 )
      {
        LogMsgHR(v23, (wchar_t *)L"rt/rtctxex", 0x78u);
        CHCryptKey::~CHCryptKey((CHCryptKey *)v31);
        free(Block);
        P<UserSecurityContext>::~P<UserSecurityContext>(&v29);
        return v24;
      }
    }
    else if ( !v22 )
    {
      v25 = UserSecurityContext::ExportPrivateKey(v12);
      v26 = v25;
      if ( v25 < 0 )
      {
        LogMsgHR(v25, (wchar_t *)L"rt/rtctxex", 0x8Cu);
        CHCryptKey::~CHCryptKey((CHCryptKey *)v31);
        free(Block);
        P<UserSecurityContext>::~P<UserSecurityContext>(&v29);
        return v26;
      }
    }
    *a3 = v13;
    v29 = 0;
    CHCryptKey::~CHCryptKey((CHCryptKey *)v31);
    free(Block);
    P<UserSecurityContext>::~P<UserSecurityContext>(&v29);
    return 0;
  }
  else if ( v16 == -1072824273 )
  {
    *a3 = v13;
    v29 = 0;
    CHCryptKey::~CHCryptKey((CHCryptKey *)v31);
    free(Block);
    P<UserSecurityContext>::~P<UserSecurityContext>(&v29);
    return 0;
  }
  else
  {
    LogMsgHR(v16, (wchar_t *)L"rt/rtctxex", 0x46u);
    CHCryptKey::~CHCryptKey((CHCryptKey *)v31);
    free(Block);
    P<UserSecurityContext>::~P<UserSecurityContext>(&v29);
    return v17;
  }
}

```

## disassembly

```asm
0x180017728  push    rbx
0x18001772a  push    rsi
0x18001772b  push    rdi
0x18001772c  push    r12
0x18001772e  push    r13
0x180017730  push    r14
0x180017732  push    r15
0x180017734  sub     rsp, 40h
0x180017738  mov     r12b, r9b
0x18001773b  mov     r14, r8
0x18001773e  mov     r13d, edx
0x180017741  mov     r15, rcx
0x180017744  call    ?RtpOneTimeThreadInit@@YAJXZ; RtpOneTimeThreadInit(void)
0x180017749  mov     ebx, eax
0x18001774b  test    eax, eax
0x18001774d  jns     short loc_180017768
0x18001774f  mov     r8d, 44Fh; unsigned __int16
0x180017755  lea     rdx, aRtRtctxex; "rt/rtctxex"
0x18001775c  mov     ecx, eax; int
0x18001775e  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180017763  jmp     loc_180017A54
0x180017768  mov     ecx, 0C8h; unsigned __int64
0x18001776d  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180017772  mov     [rsp+78h+var_40], rax
0x180017777  test    rax, rax
0x18001777a  jz      short loc_180017789
0x18001777c  mov     rcx, rax; this
0x18001777f  call    ??0UserSecurityContext@@QEAA@XZ; UserSecurityContext::UserSecurityContext(void)
0x180017784  mov     rbx, rax
0x180017787  jmp     short loc_18001778B
0x180017789  xor     ebx, ebx
0x18001778b  mov     [rsp+78h+var_50], rbx
0x180017790  mov     rdx, rbx; void *
0x180017793  call    ?AddContext@CContextMap@@QEAAKPEAX@Z; CContextMap::AddContext(void *)
0x180017798  movsxd  rsi, eax
0x18001779b  mov     [rsp+78h+Block], 0
0x1800177a4  mov     [rsp+78h+var_40], 0
0x1800177ad  mov     rcx, rbx; this
0x1800177b0  call    ?InitializeUserInfo@RTSecurityContextBase@@QEAAJXZ; RTSecurityContextBase::InitializeUserInfo(void)
0x1800177b5  mov     edi, eax
0x1800177b7  test    eax, eax
0x1800177b9  jns     short loc_1800177F8
0x1800177bb  mov     r8d, 3Ch ; '<'; unsigned __int16
0x1800177c1  lea     rdx, aRtRtctxex; "rt/rtctxex"
0x1800177c8  mov     ecx, eax; int
0x1800177ca  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800177cf  nop
0x1800177d0  lea     rcx, [rsp+78h+var_40]; this
0x1800177d5  call    ??1CHCryptKey@@QEAA@XZ; CHCryptKey::~CHCryptKey(void)
0x1800177da  nop
0x1800177db  mov     rcx, [rsp+78h+Block]; Block
0x1800177e0  call    cs:__imp_free
0x1800177e6  nop
0x1800177e7  lea     rcx, [rsp+78h+var_50]
0x1800177ec  call    ??1?$P@VUserSecurityContext@@@@QEAA@XZ; P<UserSecurityContext>::~P<UserSecurityContext>(void)
0x1800177f1  mov     eax, edi
0x1800177f3  jmp     loc_180017A56
0x1800177f8  test    r15, r15
0x1800177fb  jz      short loc_18001780B
0x1800177fd  mov     r8d, r13d; unsigned int
0x180017800  mov     rdx, r15; void *
0x180017803  mov     rcx, rbx; this
0x180017806  call    ?AllocateAndCopyUserCert@RTSecurityContextBase@@IEAAXPEAXK@Z; RTSecurityContextBase::AllocateAndCopyUserCert(void *,ulong)
0x18001780b  xor     r13d, r13d
0x18001780e  test    r12b, r12b
0x180017811  jnz     loc_18001789F
0x180017817  mov     rax, [rbx]
0x18001781a  xor     edx, edx
0x18001781c  mov     rcx, rbx
0x18001781f  mov     rax, [rax]
0x180017822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017827  mov     edi, eax
0x180017829  test    eax, eax
0x18001782b  jns     short loc_18001789F
0x18001782d  cmp     eax, 0C00E002Fh
0x180017832  jz      short loc_18001786F
0x180017834  lea     r8d, [r13+46h]; unsigned __int16
0x180017838  lea     rdx, aRtRtctxex; "rt/rtctxex"
0x18001783f  mov     ecx, eax; int
0x180017841  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180017846  nop
0x180017847  lea     rcx, [rsp+78h+var_40]; this
0x18001784c  call    ??1CHCryptKey@@QEAA@XZ; CHCryptKey::~CHCryptKey(void)
0x180017851  nop
0x180017852  mov     rcx, [rsp+78h+Block]; Block
0x180017857  call    cs:__imp_free
0x18001785d  nop
0x18001785e  lea     rcx, [rsp+78h+var_50]
0x180017863  call    ??1?$P@VUserSecurityContext@@@@QEAA@XZ; P<UserSecurityContext>::~P<UserSecurityContext>(void)
0x180017868  mov     eax, edi
0x18001786a  jmp     loc_180017A56
0x18001786f  mov     [r14], rsi
0x180017872  mov     [rsp+78h+var_50], r13
0x180017877  lea     rcx, [rsp+78h+var_40]; this
0x18001787c  call    ??1CHCryptKey@@QEAA@XZ; CHCryptKey::~CHCryptKey(void)
0x180017881  nop
0x180017882  mov     rcx, [rsp+78h+Block]; Block
0x180017887  call    cs:__imp_free
0x18001788d  nop
0x18001788e  lea     rcx, [rsp+78h+var_50]
0x180017893  call    ??1?$P@VUserSecurityContext@@@@QEAA@XZ; P<UserSecurityContext>::~P<UserSecurityContext>(void)
0x180017898  xor     eax, eax
0x18001789a  jmp     loc_180017A56
0x18001789f  mov     [rsp+78h+var_58], r13d
0x1800178a4  xor     r9d, r9d
0x1800178a7  lea     r8, [rsp+78h+var_58]
0x1800178ac  lea     rdx, [rsp+78h+Block]
0x1800178b1  xor     ecx, ecx
0x1800178b3  call    cs:__imp_?MQSec_GetThreadUserSid@@YAJHPEAPEAXPEAKH@Z; MQSec_GetThreadUserSid(int,void * *,ulong *,int)
0x1800178b9  mov     edi, eax
0x1800178bb  test    eax, eax
0x1800178bd  jns     short loc_1800178FC
0x1800178bf  mov     r8d, 5Ah ; 'Z'; unsigned __int16
0x1800178c5  lea     rdx, aRtRtctxex; "rt/rtctxex"
0x1800178cc  mov     ecx, eax; int
0x1800178ce  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800178d3  nop
0x1800178d4  lea     rcx, [rsp+78h+var_40]; this
0x1800178d9  call    ??1CHCryptKey@@QEAA@XZ; CHCryptKey::~CHCryptKey(void)
0x1800178de  nop
0x1800178df  mov     rcx, [rsp+78h+Block]; Block
0x1800178e4  call    cs:__imp_free
0x1800178ea  nop
0x1800178eb  lea     rcx, [rsp+78h+var_50]
0x1800178f0  call    ??1?$P@VUserSecurityContext@@@@QEAA@XZ; P<UserSecurityContext>::~P<UserSecurityContext>(void)
0x1800178f5  mov     eax, edi
0x1800178f7  jmp     loc_180017A56
0x1800178fc  mov     rcx, [rsp+78h+Block]; pSid1
0x180017901  call    ?SameAsProcessSid@@YAHPEAX@Z; SameAsProcessSid(void *)
0x180017906  mov     r15d, eax
0x180017909  test    r12b, r12b
0x18001790c  jz      loc_18001799F
0x180017912  mov     rcx, [rbx]
0x180017915  test    eax, eax
0x180017917  setz    dl
0x18001791a  mov     rax, [rcx]
0x18001791d  mov     rcx, rbx
0x180017920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017925  mov     edi, eax
0x180017927  test    eax, eax
0x180017929  jns     short loc_18001799F
0x18001792b  cmp     eax, 0C00E002Fh
0x180017930  jz      short loc_18001796F
0x180017932  mov     r8d, 78h ; 'x'; unsigned __int16
0x180017938  lea     rdx, aRtRtctxex; "rt/rtctxex"
0x18001793f  mov     ecx, eax; int
0x180017941  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180017946  nop
0x180017947  lea     rcx, [rsp+78h+var_40]; this
0x18001794c  call    ??1CHCryptKey@@QEAA@XZ; CHCryptKey::~CHCryptKey(void)
0x180017951  nop
0x180017952  mov     rcx, [rsp+78h+Block]; Block
0x180017957  call    cs:__imp_free
0x18001795d  nop
0x18001795e  lea     rcx, [rsp+78h+var_50]
0x180017963  call    ??1?$P@VUserSecurityContext@@@@QEAA@XZ; P<UserSecurityContext>::~P<UserSecurityContext>(void)
0x180017968  mov     eax, edi
0x18001796a  jmp     loc_180017A56
0x18001796f  mov     [r14], rsi
0x180017972  mov     [rsp+78h+var_50], r13
0x180017977  lea     rcx, [rsp+78h+var_40]; this
0x18001797c  call    ??1CHCryptKey@@QEAA@XZ; CHCryptKey::~CHCryptKey(void)
0x180017981  nop
0x180017982  mov     rcx, [rsp+78h+Block]; Block
0x180017987  call    cs:__imp_free
0x18001798d  nop
0x18001798e  lea     rcx, [rsp+78h+var_50]
0x180017993  call    ??1?$P@VUserSecurityContext@@@@QEAA@XZ; P<UserSecurityContext>::~P<UserSecurityContext>(void)
0x180017998  xor     eax, eax
0x18001799a  jmp     loc_180017A56
0x18001799f  test    r15d, r15d
0x1800179a2  jnz     short loc_1800179EC
0x1800179a4  mov     rcx, rbx; this
0x1800179a7  call    ?ExportPrivateKey@UserSecurityContext@@QEAAJXZ; UserSecurityContext::ExportPrivateKey(void)
0x1800179ac  mov     ebx, eax
0x1800179ae  test    eax, eax
0x1800179b0  jns     short loc_1800179EC
0x1800179b2  mov     r8d, 8Ch; unsigned __int16
0x1800179b8  lea     rdx, aRtRtctxex; "rt/rtctxex"
0x1800179bf  mov     ecx, eax; int
0x1800179c1  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800179c6  nop
0x1800179c7  lea     rcx, [rsp+78h+var_40]; this
0x1800179cc  call    ??1CHCryptKey@@QEAA@XZ; CHCryptKey::~CHCryptKey(void)
0x1800179d1  nop
0x1800179d2  mov     rcx, [rsp+78h+Block]; Block
0x1800179d7  call    cs:__imp_free
0x1800179dd  nop
0x1800179de  lea     rcx, [rsp+78h+var_50]
0x1800179e3  call    ??1?$P@VUserSecurityContext@@@@QEAA@XZ; P<UserSecurityContext>::~P<UserSecurityContext>(void)
0x1800179e8  mov     eax, ebx
0x1800179ea  jmp     short loc_180017A56
0x1800179ec  mov     [r14], rsi
0x1800179ef  mov     [rsp+78h+var_50], r13
0x1800179f4  lea     rcx, [rsp+78h+var_40]; this
0x1800179f9  call    ??1CHCryptKey@@QEAA@XZ; CHCryptKey::~CHCryptKey(void)
0x1800179fe  nop
0x1800179ff  mov     rcx, [rsp+78h+Block]; Block
0x180017a04  call    cs:__imp_free
0x180017a0a  nop
0x180017a0b  lea     rcx, [rsp+78h+var_50]
0x180017a10  call    ??1?$P@VUserSecurityContext@@@@QEAA@XZ; P<UserSecurityContext>::~P<UserSecurityContext>(void)
0x180017a15  xor     eax, eax
0x180017a17  jmp     short loc_180017A56
0x180017a19  mov     r8d, 96h; unsigned __int16
0x180017a1f  lea     rdx, aRtRtctxex; "rt/rtctxex"
0x180017a26  mov     ebx, 0C00E0006h
0x180017a2b  mov     ecx, ebx; int
0x180017a2d  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180017a32  nop
0x180017a33  lea     rcx, [rsp+78h+var_40]; this
0x180017a38  call    ??1CHCryptKey@@QEAA@XZ; CHCryptKey::~CHCryptKey(void)
0x180017a3d  nop
0x180017a3e  mov     rcx, [rsp+78h+Block]; Block
0x180017a43  call    cs:__imp_free
0x180017a49  nop
0x180017a4a  lea     rcx, [rsp+78h+var_50]
0x180017a4f  call    ??1?$P@VUserSecurityContext@@@@QEAA@XZ; P<UserSecurityContext>::~P<UserSecurityContext>(void)
0x180017a54  mov     eax, ebx
0x180017a56  add     rsp, 40h
0x180017a5a  pop     r15
0x180017a5c  pop     r14
0x180017a5e  pop     r13
0x180017a60  pop     r12
0x180017a62  pop     rdi
0x180017a63  pop     rsi
0x180017a64  pop     rbx
0x180017a65  retn
```
