# CSecureableObject::SetSD(ulong,void *)

- ea: `0x18002087c`
- end: `0x180020c96`
- name: `?SetSD@CSecureableObject@@QEAAJKPEAX@Z`
- size: `1050`
- prototype: `__int64 __fastcall(CSecureableObject *__hidden this, unsigned int, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001cce4`

## callees

- `0x18000d1f0`
- `0x18000f35c`
- `0x18002057c`
- `0x1800205c8`
- `0x18002087c`
- `0x18002c61c`
- `0x18009bd1c`

## import_xrefs

- `msvcrt!free` at `0x18002099c`
- `msvcrt!free` at `0x1800209a7`
- `msvcrt!free` at `0x180020a39`
- `msvcrt!free` at `0x180020a44`
- `msvcrt!free` at `0x180020ac4`
- `msvcrt!free` at `0x180020acf`
- `msvcrt!free` at `0x180020b74`
- `msvcrt!free` at `0x180020b7f`
- `msvcrt!free` at `0x180020c1b`
- `msvcrt!free` at `0x180020c30`
- `msvcrt!free` at `0x180020c3b`
- `msvcrt!free` at `0x180020c4a`
- `msvcrt!free` at `0x180020c57`
- `msvcrt!free` at `0x180020c6c`
- `msvcrt!free` at `0x180020c77`
- `msvcrt!free` at `0x18002099c`
- `msvcrt!free` at `0x1800209a7`
- `msvcrt!free` at `0x180020a39`
- `msvcrt!free` at `0x180020a44`
- `msvcrt!free` at `0x180020ac4`
- `msvcrt!free` at `0x180020acf`
- `msvcrt!free` at `0x180020b74`
- `msvcrt!free` at `0x180020b7f`
- `msvcrt!free` at `0x180020c1b`
- `msvcrt!free` at `0x180020c30`
- `msvcrt!free` at `0x180020c3b`
- `msvcrt!free` at `0x180020c4a`
- `msvcrt!free` at `0x180020c57`
- `msvcrt!free` at `0x180020c6c`
- `msvcrt!free` at `0x180020c77`
- `ADVAPI32!MakeSelfRelativeSD` at `0x180020aec`
- `ADVAPI32!MakeSelfRelativeSD` at `0x180020ba5`
- `ADVAPI32!MakeSelfRelativeSD` at `0x180020aec`
- `ADVAPI32!MakeSelfRelativeSD` at `0x180020ba5`
- `KERNEL32!GetLastError` at `0x180020af2`
- `KERNEL32!GetLastError` at `0x180020b01`
- `KERNEL32!GetLastError` at `0x180020bb3`
- `KERNEL32!GetLastError` at `0x180020af2`
- `KERNEL32!GetLastError` at `0x180020b01`
- `KERNEL32!GetLastError` at `0x180020bb3`
- `mqsec!MQSec_GetDefaultPrivateQueueSecurityDescriptor` at `0x180020977`
- `mqsec!MQSec_GetDefaultPrivateQueueSecurityDescriptor` at `0x180020977`
- `mqsec!MQSec_GetLocalMachineSid` at `0x180020956`
- `mqsec!MQSec_GetLocalMachineSid` at `0x180020956`
- `mqsec!MQSec_ConvertSDToNT4Format` at `0x18002091c`
- `mqsec!MQSec_ConvertSDToNT4Format` at `0x18002091c`
- `mqsec!MQSec_CopySecurityDescriptor` at `0x180020a5e`
- `mqsec!MQSec_CopySecurityDescriptor` at `0x180020a5e`
- `mqsec!MQSec_MakeAbsoluteSD` at `0x1800209d3`
- `mqsec!MQSec_MakeAbsoluteSD` at `0x1800209d3`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CSecureableObject::SetSD(CSecureableObject *this, unsigned int a2, struct _SECURITY_DESCRIPTOR *a3)
{
  signed int LastError; // ebx
  unsigned __int16 v7; // r8
  int v9; // r8d
  unsigned int v10; // edx
  struct _SECURITY_DESCRIPTOR *v11; // rbx
  int v12; // eax
  void *LocalMachineSid; // rax
  int DefaultPrivateQueueSecurityDescriptor; // eax
  bool v15; // sf
  void *v16; // rbx
  signed int v17; // edi
  bool v18; // sf
  void *Block; // [rsp+30h] [rbp-40h] BYREF
  void *v20; // [rsp+38h] [rbp-38h] BYREF
  _OWORD v21[2]; // [rsp+40h] [rbp-30h] BYREF
  PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor; // [rsp+60h] [rbp-10h]
  DWORD dwBufferLength; // [rsp+90h] [rbp+20h] BYREF
  void *v24; // [rsp+A8h] [rbp+38h] BYREF

  LastError = *((_DWORD *)this + 5);
  if ( LastError < 0 )
  {
    v7 = 1110;
LABEL_3:
    LogMsgHR(LastError, (wchar_t *)L"csecobj", v7);
    return (unsigned int)LastError;
  }
  v9 = ((a2 & 1) << 19) | 0x40000;
  if ( (a2 & 4) == 0 )
    v9 = (a2 & 1) << 19;
  v10 = v9 | 0x1000000;
  if ( (a2 & 8) == 0 )
    v10 = v9;
  LastError = CSecureableObject::AccessCheck(this, v10);
  if ( LastError < 0 )
  {
    v7 = 30;
    goto LABEL_3;
  }
  v11 = 0;
  v20 = 0;
  if ( a3 )
  {
    LODWORD(v24) = 0;
    v12 = MQSec_ConvertSDToNT4Format(1u, a3, (unsigned int *)&v24, (struct _SECURITY_DESCRIPTOR **)&v20, a2);
    if ( v12 >= 0 )
    {
      v11 = (struct _SECURITY_DESCRIPTOR *)v20;
      if ( v12 != 1074662402 )
        goto LABEL_16;
    }
    else
    {
      LogMsgHR(v12, (wchar_t *)L"csecobj", 0xC6u);
    }
    v11 = a3;
  }
LABEL_16:
  Block = 0;
  LocalMachineSid = MQSec_GetLocalMachineSid(0, 0);
  DefaultPrivateQueueSecurityDescriptor = MQSec_GetDefaultPrivateQueueSecurityDescriptor(
                                            &Block,
                                            1,
                                            v11,
                                            0,
                                            0,
                                            LocalMachineSid);
  LastError = DefaultPrivateQueueSecurityDescriptor;
  if ( DefaultPrivateQueueSecurityDescriptor < 0 )
  {
    LogMsgHR(DefaultPrivateQueueSecurityDescriptor, (wchar_t *)L"csecobj", 0x28u);
    free(Block);
    free(v20);
    return (unsigned int)LastError;
  }
  memset(v21, 0, sizeof(v21));
  pAbsoluteSecurityDescriptor = 0;
  if ( !MQSec_MakeAbsoluteSD(*((void **)this + 1), (struct CAbsSecurityDsecripror *)v21) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 13, WPP_4da6f04276133d0ae63c467c728c89f9_Traceguids);
    LastError = -1072824287;
    LogMsgHR(-1072824287, (wchar_t *)L"csecobj", 0x461u);
    CAbsSecurityDsecripror::~CAbsSecurityDsecripror((CAbsSecurityDsecripror *)v21);
    free(Block);
    free(v20);
    return (unsigned int)LastError;
  }
  if ( !(unsigned int)MQSec_CopySecurityDescriptor(pAbsoluteSecurityDescriptor, Block, a2, 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 14, WPP_4da6f04276133d0ae63c467c728c89f9_Traceguids);
    LastError = -1072824287;
    LogMsgHR(-1072824287, (wchar_t *)L"csecobj", 0x462u);
    CAbsSecurityDsecripror::~CAbsSecurityDsecripror((CAbsSecurityDsecripror *)v21);
    free(Block);
    free(v20);
    return (unsigned int)LastError;
  }
  dwBufferLength = 0;
  MakeSelfRelativeSD(pAbsoluteSecurityDescriptor, 0, &dwBufferLength);
  if ( GetLastError() != 122 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 32),
        15,
        WPP_4da6f04276133d0ae63c467c728c89f9_Traceguids,
        (unsigned int)LastError);
    v15 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v15 = LastError < 0;
    }
    if ( v15 )
      LogMsgHR(LastError, (wchar_t *)L"csecobj", 0x463u);
    CAbsSecurityDsecripror::~CAbsSecurityDsecripror((CAbsSecurityDsecripror *)v21);
    free(Block);
    free(v20);
    return (unsigned int)LastError;
  }
  v16 = MmAllocate(dwBufferLength);
  v24 = v16;
  if ( MakeSelfRelativeSD(pAbsoluteSecurityDescriptor, v16, &dwBufferLength) )
  {
    free(*((void **)this + 1));
    *((_QWORD *)this + 1) = v16;
    free(0);
    CAbsSecurityDsecripror::~CAbsSecurityDsecripror((CAbsSecurityDsecripror *)v21);
    free(Block);
    free(v20);
    return 0;
  }
  else
  {
    v17 = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 32),
        16,
        WPP_4da6f04276133d0ae63c467c728c89f9_Traceguids,
        (unsigned int)v17);
    v18 = v17 < 0;
    if ( v17 > 0 )
    {
      v17 = (unsigned __int16)v17 | 0x80070000;
      v18 = v17 < 0;
    }
    if ( v18 )
      LogMsgHR(v17, (wchar_t *)L"csecobj", 0x464u);
    free(v16);
    CAbsSecurityDsecripror::~CAbsSecurityDsecripror((CAbsSecurityDsecripror *)v21);
    free(Block);
    free(v20);
    return (unsigned int)v17;
  }
}

```

## disassembly

```asm
0x18002087c  mov     [rsp-18h+arg_8], rbx
0x180020881  mov     [rsp-18h+arg_10], rdi
0x180020886  push    rbp
0x180020887  push    r14
0x180020889  push    r15
0x18002088b  mov     rbp, rsp
0x18002088e  sub     rsp, 70h
0x180020892  mov     r14, r8
0x180020895  mov     r15d, edx
0x180020898  mov     rdi, rcx
0x18002089b  mov     ebx, [rcx+14h]
0x18002089e  test    ebx, ebx
0x1800208a0  jns     short loc_1800208BD
0x1800208a2  mov     r8d, 456h; unsigned __int16
0x1800208a8  lea     rdx, aCsecobj; "csecobj"
0x1800208af  mov     ecx, ebx; int
0x1800208b1  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800208b6  mov     eax, ebx
0x1800208b8  jmp     loc_180020C80
0x1800208bd  mov     ecx, r15d
0x1800208c0  and     ecx, 1
0x1800208c3  shl     ecx, 13h
0x1800208c6  mov     r8d, ecx
0x1800208c9  bts     r8d, 12h
0x1800208ce  test    r15b, 4
0x1800208d2  cmovz   r8d, ecx
0x1800208d6  mov     edx, r8d
0x1800208d9  bts     edx, 18h
0x1800208dd  test    r15b, 8
0x1800208e1  cmovz   edx, r8d; unsigned int
0x1800208e5  mov     rcx, rdi; this
0x1800208e8  call    ?AccessCheck@CSecureableObject@@QEAAJK@Z; CSecureableObject::AccessCheck(ulong)
0x1800208ed  mov     ebx, eax
0x1800208ef  test    eax, eax
0x1800208f1  jns     short loc_1800208FB
0x1800208f3  mov     r8d, 1Eh
0x1800208f9  jmp     short loc_1800208A8
0x1800208fb  xor     ebx, ebx
0x1800208fd  mov     [rbp+var_38], rbx
0x180020901  test    r14, r14
0x180020904  jz      short loc_18002094A
0x180020906  mov     dword ptr [rbp+arg_18], ebx
0x180020909  mov     [rsp+70h+var_50], r15d
0x18002090e  lea     r9, [rbp+var_38]
0x180020912  lea     r8, [rbp+arg_18]
0x180020916  mov     rdx, r14
0x180020919  lea     ecx, [rbx+1]
0x18002091c  call    cs:__imp_?MQSec_ConvertSDToNT4Format@@YAJKPEAU_SECURITY_DESCRIPTOR@@PEAKPEAPEAU1@K@Z; MQSec_ConvertSDToNT4Format(ulong,_SECURITY_DESCRIPTOR *,ulong *,_SECURITY_DESCRIPTOR * *,ulong)
0x180020922  test    eax, eax
0x180020924  jns     short loc_18002093C
0x180020926  mov     r8d, 0C6h; unsigned __int16
0x18002092c  lea     rdx, aCsecobj; "csecobj"
0x180020933  mov     ecx, eax; int
0x180020935  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18002093a  jmp     short loc_180020947
0x18002093c  cmp     eax, 400E0C02h
0x180020941  mov     rbx, [rbp+var_38]
0x180020945  jnz     short loc_18002094A
0x180020947  mov     rbx, r14
0x18002094a  mov     [rbp+Block], 0
0x180020952  xor     edx, edx
0x180020954  xor     ecx, ecx
0x180020956  call    cs:__imp_?MQSec_GetLocalMachineSid@@YAPEAXHPEAK@Z; MQSec_GetLocalMachineSid(int,ulong *)
0x18002095c  mov     [rsp+70h+var_48], rax
0x180020961  mov     [rsp+70h+var_50], 0
0x180020969  xor     r9d, r9d
0x18002096c  mov     r8, rbx
0x18002096f  lea     edx, [r9+1]
0x180020973  lea     rcx, [rbp+Block]
0x180020977  call    cs:__imp_?MQSec_GetDefaultPrivateQueueSecurityDescriptor@@YAJPEAPEAXHPEAXKW4enumDaclType@@1@Z; MQSec_GetDefaultPrivateQueueSecurityDescriptor(void * *,int,void *,ulong,enumDaclType,void *)
0x18002097d  mov     ebx, eax
0x18002097f  test    eax, eax
0x180020981  jns     short loc_1800209B3
0x180020983  mov     r8d, 28h ; '('; unsigned __int16
0x180020989  lea     rdx, aCsecobj; "csecobj"
0x180020990  mov     ecx, eax; int
0x180020992  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180020997  nop
0x180020998  mov     rcx, [rbp+Block]; Block
0x18002099c  call    cs:__imp_free
0x1800209a2  nop
0x1800209a3  mov     rcx, [rbp+var_38]; Block
0x1800209a7  call    cs:__imp_free
0x1800209ad  nop
0x1800209ae  jmp     loc_1800208B6
0x1800209b3  xorps   xmm0, xmm0
0x1800209b6  movdqu  [rbp+var_30], xmm0
0x1800209bb  xorps   xmm1, xmm1
0x1800209be  movdqu  [rbp+var_20], xmm1
0x1800209c3  mov     [rbp+pAbsoluteSecurityDescriptor], 0
0x1800209cb  lea     rdx, [rbp+var_30]
0x1800209cf  mov     rcx, [rdi+8]
0x1800209d3  call    cs:__imp_?MQSec_MakeAbsoluteSD@@YA_NPEAXPEAUCAbsSecurityDsecripror@@@Z; MQSec_MakeAbsoluteSD(void *,CAbsSecurityDsecripror *)
0x1800209d9  test    al, al
0x1800209db  jnz     short loc_180020A50
0x1800209dd  lea     rax, WPP_GLOBAL_Control
0x1800209e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800209eb  cmp     rcx, rax
0x1800209ee  jz      short loc_180020A11
0x1800209f0  test    byte ptr [rcx+10Ch], 1
0x1800209f7  jz      short loc_180020A11
0x1800209f9  mov     edx, 0Dh
0x1800209fe  lea     r8, WPP_4da6f04276133d0ae63c467c728c89f9_Traceguids
0x180020a05  mov     rcx, [rcx+100h]
0x180020a0c  call    WPP_SF_
0x180020a11  mov     r8d, 461h; unsigned __int16
0x180020a17  lea     rdx, aCsecobj; "csecobj"
0x180020a1e  mov     ebx, 0C00E0021h
0x180020a23  mov     ecx, ebx; int
0x180020a25  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180020a2a  nop
0x180020a2b  lea     rcx, [rbp+var_30]; this
0x180020a2f  call    ??1CAbsSecurityDsecripror@@QEAA@XZ; CAbsSecurityDsecripror::~CAbsSecurityDsecripror(void)
0x180020a34  nop
0x180020a35  mov     rcx, [rbp+Block]; Block
0x180020a39  call    cs:__imp_free
0x180020a3f  nop
0x180020a40  mov     rcx, [rbp+var_38]; Block
0x180020a44  call    cs:__imp_free
0x180020a4a  nop
0x180020a4b  jmp     loc_1800208B6
0x180020a50  xor     r9d, r9d
0x180020a53  mov     r8d, r15d
0x180020a56  mov     rdx, [rbp+Block]
0x180020a5a  mov     rcx, [rbp+pAbsoluteSecurityDescriptor]
0x180020a5e  call    cs:__imp_?MQSec_CopySecurityDescriptor@@YAHPEAX0KW4enumCopyControl@@@Z; MQSec_CopySecurityDescriptor(void *,void *,ulong,enumCopyControl)
0x180020a64  test    eax, eax
0x180020a66  jnz     short loc_180020ADB
0x180020a68  lea     rax, WPP_GLOBAL_Control
0x180020a6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180020a76  cmp     rcx, rax
0x180020a79  jz      short loc_180020A9C
0x180020a7b  test    byte ptr [rcx+10Ch], 1
0x180020a82  jz      short loc_180020A9C
0x180020a84  mov     edx, 0Eh
0x180020a89  lea     r8, WPP_4da6f04276133d0ae63c467c728c89f9_Traceguids
0x180020a90  mov     rcx, [rcx+100h]
0x180020a97  call    WPP_SF_
0x180020a9c  mov     r8d, 462h; unsigned __int16
0x180020aa2  lea     rdx, aCsecobj; "csecobj"
0x180020aa9  mov     ebx, 0C00E0021h
0x180020aae  mov     ecx, ebx; int
0x180020ab0  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180020ab5  nop
0x180020ab6  lea     rcx, [rbp+var_30]; this
0x180020aba  call    ??1CAbsSecurityDsecripror@@QEAA@XZ; CAbsSecurityDsecripror::~CAbsSecurityDsecripror(void)
0x180020abf  nop
0x180020ac0  mov     rcx, [rbp+Block]; Block
0x180020ac4  call    cs:__imp_free
0x180020aca  nop
0x180020acb  mov     rcx, [rbp+var_38]; Block
0x180020acf  call    cs:__imp_free
0x180020ad5  nop
0x180020ad6  jmp     loc_1800208B6
0x180020adb  mov     [rbp+dwBufferLength], 0
0x180020ae2  lea     r8, [rbp+dwBufferLength]; lpdwBufferLength
0x180020ae6  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x180020ae8  mov     rcx, [rbp+pAbsoluteSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x180020aec  call    cs:__imp_MakeSelfRelativeSD
0x180020af2  call    cs:__imp_GetLastError
0x180020af8  cmp     eax, 7Ah ; 'z'
0x180020afb  jz      loc_180020B8B
0x180020b01  call    cs:__imp_GetLastError
0x180020b07  mov     ebx, eax
0x180020b09  lea     rax, WPP_GLOBAL_Control
0x180020b10  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b17  cmp     rcx, rax
0x180020b1a  jz      short loc_180020B40
0x180020b1c  test    byte ptr [rcx+10Ch], 1
0x180020b23  jz      short loc_180020B40
0x180020b25  mov     edx, 0Fh
0x180020b2a  mov     r9d, ebx
0x180020b2d  lea     r8, WPP_4da6f04276133d0ae63c467c728c89f9_Traceguids
0x180020b34  mov     rcx, [rcx+100h]
0x180020b3b  call    WPP_SF_d
0x180020b40  test    ebx, ebx
0x180020b42  jle     short loc_180020B4F
0x180020b44  movzx   ebx, bx
0x180020b47  or      ebx, 80070000h
0x180020b4d  test    ebx, ebx
0x180020b4f  jns     short loc_180020B66
0x180020b51  mov     r8d, 463h; unsigned __int16
0x180020b57  lea     rdx, aCsecobj; "csecobj"
0x180020b5e  mov     ecx, ebx; int
0x180020b60  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180020b65  nop
0x180020b66  lea     rcx, [rbp+var_30]; this
0x180020b6a  call    ??1CAbsSecurityDsecripror@@QEAA@XZ; CAbsSecurityDsecripror::~CAbsSecurityDsecripror(void)
0x180020b6f  nop
0x180020b70  mov     rcx, [rbp+Block]; Block
0x180020b74  call    cs:__imp_free
0x180020b7a  nop
0x180020b7b  mov     rcx, [rbp+var_38]; Block
0x180020b7f  call    cs:__imp_free
0x180020b85  nop
0x180020b86  jmp     loc_1800208B6
0x180020b8b  mov     ecx, [rbp+dwBufferLength]; unsigned __int64
0x180020b8e  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180020b93  mov     rbx, rax
0x180020b96  mov     [rbp+arg_18], rax
0x180020b9a  lea     r8, [rbp+dwBufferLength]; lpdwBufferLength
0x180020b9e  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x180020ba1  mov     rcx, [rbp+pAbsoluteSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x180020ba5  call    cs:__imp_MakeSelfRelativeSD
0x180020bab  test    eax, eax
0x180020bad  jnz     loc_180020C46
0x180020bb3  call    cs:__imp_GetLastError
0x180020bb9  mov     edi, eax
0x180020bbb  lea     rax, WPP_GLOBAL_Control
0x180020bc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180020bc9  cmp     rcx, rax
0x180020bcc  jz      short loc_180020BF2
0x180020bce  test    byte ptr [rcx+10Ch], 1
0x180020bd5  jz      short loc_180020BF2
0x180020bd7  mov     edx, 10h
0x180020bdc  mov     r9d, edi
0x180020bdf  lea     r8, WPP_4da6f04276133d0ae63c467c728c89f9_Traceguids
0x180020be6  mov     rcx, [rcx+100h]
0x180020bed  call    WPP_SF_d
0x180020bf2  test    edi, edi
0x180020bf4  jle     short loc_180020C01
0x180020bf6  movzx   edi, di
0x180020bf9  or      edi, 80070000h
0x180020bff  test    edi, edi
0x180020c01  jns     short loc_180020C18
0x180020c03  mov     r8d, 464h; unsigned __int16
0x180020c09  lea     rdx, aCsecobj; "csecobj"
0x180020c10  mov     ecx, edi; int
0x180020c12  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180020c17  nop
0x180020c18  mov     rcx, rbx; Block
0x180020c1b  call    cs:__imp_free
0x180020c21  nop
0x180020c22  lea     rcx, [rbp+var_30]; this
0x180020c26  call    ??1CAbsSecurityDsecripror@@QEAA@XZ; CAbsSecurityDsecripror::~CAbsSecurityDsecripror(void)
0x180020c2b  nop
0x180020c2c  mov     rcx, [rbp+Block]; Block
0x180020c30  call    cs:__imp_free
0x180020c36  nop
0x180020c37  mov     rcx, [rbp+var_38]; Block
0x180020c3b  call    cs:__imp_free
0x180020c41  nop
0x180020c42  mov     eax, edi
0x180020c44  jmp     short loc_180020C80
0x180020c46  mov     rcx, [rdi+8]; Block
0x180020c4a  call    cs:__imp_free
0x180020c50  nop
0x180020c51  mov     [rdi+8], rbx
0x180020c55  xor     ecx, ecx; Block
0x180020c57  call    cs:__imp_free
0x180020c5d  nop
0x180020c5e  lea     rcx, [rbp+var_30]; this
0x180020c62  call    ??1CAbsSecurityDsecripror@@QEAA@XZ; CAbsSecurityDsecripror::~CAbsSecurityDsecripror(void)
0x180020c67  nop
0x180020c68  mov     rcx, [rbp+Block]; Block
0x180020c6c  call    cs:__imp_free
0x180020c72  nop
0x180020c73  mov     rcx, [rbp+var_38]; Block
0x180020c77  call    cs:__imp_free
0x180020c7d  nop
0x180020c7e  xor     eax, eax
0x180020c80  lea     r11, [rsp+70h+var_s0]
0x180020c85  mov     rbx, [r11+28h]
0x180020c89  mov     rdi, [r11+30h]
0x180020c8d  mov     rsp, r11
0x180020c90  pop     r15
0x180020c92  pop     r14
0x180020c94  pop     rbp
0x180020c95  retn
```
