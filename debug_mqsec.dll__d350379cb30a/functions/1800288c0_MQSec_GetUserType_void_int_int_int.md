# MQSec_GetUserType(void *,int *,int *,int *)

- ea: `0x1800288c0`
- end: `0x180028a60`
- name: `?MQSec_GetUserType@@YAJPEAXPEAH11@Z`
- size: `416`
- prototype: `__int64 __fastcall(PSID pSid2, int *, int *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x180025eac`

## callees

- `0x1800049ac`
- `0x180020fe0`
- `0x1800215a8`
- `0x1800287c0`
- `0x1800288c0`
- `0x180028a70`
- `0x180028ab0`

## import_xrefs

- `msvcrt!free` at `0x180028946`
- `msvcrt!free` at `0x180028985`
- `msvcrt!free` at `0x1800289af`
- `msvcrt!free` at `0x1800289cd`
- `msvcrt!free` at `0x180028a46`
- `msvcrt!free` at `0x180028946`
- `msvcrt!free` at `0x180028985`
- `msvcrt!free` at `0x1800289af`
- `msvcrt!free` at `0x1800289cd`
- `msvcrt!free` at `0x180028a46`
- `ADVAPI32!EqualPrefixSid` at `0x180028a23`
- `ADVAPI32!EqualPrefixSid` at `0x180028a23`
- `ADVAPI32!GetSidIdentifierAuthority` at `0x1800289f4`
- `ADVAPI32!GetSidIdentifierAuthority` at `0x1800289f4`
- `ADVAPI32!EqualSid` at `0x18002896a`
- `ADVAPI32!EqualSid` at `0x1800289a0`
- `ADVAPI32!EqualSid` at `0x18002896a`
- `ADVAPI32!EqualSid` at `0x1800289a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MQSec_GetUserType(PSID pSid2, int *a2, int *a3, int *a4)
{
  PSID v7; // rbx
  void *v8; // rdi
  int ThreadUserSid; // ebx
  BOOL v11; // eax
  BOOL v12; // eax
  int IsAnonymusSid; // eax
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rax
  int v15; // ecx
  BOOL v16; // edx
  unsigned int v17; // [rsp+50h] [rbp+30h] BYREF
  unsigned __int16 v18; // [rsp+54h] [rbp+34h]
  void *Block; // [rsp+58h] [rbp+38h] BYREF

  v7 = pSid2;
  *a2 = 0;
  Block = 0;
  v8 = 0;
  if ( !pSid2 )
  {
    ThreadUserSid = MQSec_GetThreadUserSid(0, &Block, &v17, 0);
    if ( ThreadUserSid < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 32),
          36,
          &WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids,
          (unsigned int)ThreadUserSid);
      free(Block);
      return (unsigned int)ThreadUserSid;
    }
    v7 = Block;
    v8 = Block;
  }
  if ( a3 && (v11 = EqualSid(g_pSystemSid, v7), (*a3 = v11) != 0) )
  {
    if ( a4 )
      *a4 = 0;
  }
  else if ( !a4 || (v12 = EqualSid(g_pNetworkServiceSid, v7), (*a4 = v12) == 0) )
  {
    IsAnonymusSid = MQSec_IsAnonymusSid(v7);
    *a2 = IsAnonymusSid;
    if ( !IsAnonymusSid )
    {
      InitializeGuestSid();
      if ( IsDomainController() )
      {
        *a2 = MQSec_IsGuestSid(v7);
      }
      else
      {
        v17 = 0;
        v18 = 1280;
        SidIdentifierAuthority = GetSidIdentifierAuthority(v7);
        if ( SidIdentifierAuthority )
        {
          v15 = *(_DWORD *)SidIdentifierAuthority->Value - v17;
          if ( *(_DWORD *)SidIdentifierAuthority->Value == v17 )
            v15 = *(unsigned __int16 *)&SidIdentifierAuthority->Value[4] - v18;
          v16 = v15 || g_pGuestSid && EqualPrefixSid(v7, g_pGuestSid);
          *a2 = v16;
        }
      }
    }
  }
  free(v8);
  return 0;
}

```

## disassembly

```asm
0x1800288c0  mov     [rsp-28h+arg_10], rbx
0x1800288c5  push    rbp
0x1800288c6  push    rsi
0x1800288c7  push    rdi
0x1800288c8  push    r14
0x1800288ca  push    r15
0x1800288cc  mov     rbp, rsp
0x1800288cf  sub     rsp, 20h
0x1800288d3  mov     rsi, r9
0x1800288d6  mov     r15, r8
0x1800288d9  mov     r14, rdx
0x1800288dc  mov     rbx, rcx
0x1800288df  mov     dword ptr [rdx], 0
0x1800288e5  mov     [rbp+Block], 0
0x1800288ed  xor     edi, edi
0x1800288ef  test    rcx, rcx
0x1800288f2  jnz     short loc_18002895B
0x1800288f4  xor     r9d, r9d; int
0x1800288f7  lea     r8, [rbp+arg_0]; unsigned int *
0x1800288fb  lea     rdx, [rbp+Block]; void **
0x1800288ff  call    ?MQSec_GetThreadUserSid@@YAJHPEAPEAXPEAKH@Z; MQSec_GetThreadUserSid(int,void * *,ulong *,int)
0x180028904  mov     ebx, eax
0x180028906  test    eax, eax
0x180028908  jns     short loc_180028954
0x18002890a  lea     rax, WPP_GLOBAL_Control
0x180028911  mov     rcx, cs:WPP_GLOBAL_Control
0x180028918  cmp     rcx, rax
0x18002891b  jz      short loc_180028942
0x18002891d  lea     edx, [rdi+1]
0x180028920  test    [rcx+10Ch], dl
0x180028926  jz      short loc_180028942
0x180028928  lea     edx, [rdi+24h]
0x18002892b  mov     r9d, ebx
0x18002892e  lea     r8, WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids
0x180028935  mov     rcx, [rcx+100h]
0x18002893c  call    WPP_SF_d
0x180028941  nop
0x180028942  mov     rcx, [rbp+Block]; Block
0x180028946  call    cs:__imp_free
0x18002894c  nop
0x18002894d  mov     eax, ebx
0x18002894f  jmp     loc_180028A4F
0x180028954  mov     rbx, [rbp+Block]
0x180028958  mov     rdi, rbx
0x18002895b  test    r15, r15
0x18002895e  jz      short loc_180028991
0x180028960  mov     rdx, rbx; pSid2
0x180028963  mov     rcx, cs:?g_pSystemSid@@3PEAXEA; pSid1
0x18002896a  call    cs:__imp_EqualSid
0x180028970  mov     [r15], eax
0x180028973  test    eax, eax
0x180028975  jz      short loc_180028991
0x180028977  test    rsi, rsi
0x18002897a  jz      short loc_180028982
0x18002897c  mov     dword ptr [rsi], 0
0x180028982  mov     rcx, rdi; Block
0x180028985  call    cs:__imp_free
0x18002898b  nop
0x18002898c  jmp     loc_180028A4D
0x180028991  test    rsi, rsi
0x180028994  jz      short loc_1800289BB
0x180028996  mov     rdx, rbx; pSid2
0x180028999  mov     rcx, cs:?g_pNetworkServiceSid@@3PEAXEA; pSid1
0x1800289a0  call    cs:__imp_EqualSid
0x1800289a6  mov     [rsi], eax
0x1800289a8  test    eax, eax
0x1800289aa  jz      short loc_1800289BB
0x1800289ac  mov     rcx, rdi; Block
0x1800289af  call    cs:__imp_free
0x1800289b5  nop
0x1800289b6  jmp     loc_180028A4D
0x1800289bb  mov     rcx, rbx; pSid2
0x1800289be  call    ?MQSec_IsAnonymusSid@@YAHPEAX@Z; MQSec_IsAnonymusSid(void *)
0x1800289c3  mov     [r14], eax
0x1800289c6  test    eax, eax
0x1800289c8  jz      short loc_1800289D6
0x1800289ca  mov     rcx, rdi; Block
0x1800289cd  call    cs:__imp_free
0x1800289d3  nop
0x1800289d4  jmp     short loc_180028A4D
0x1800289d6  call    ?InitializeGuestSid@@YAXXZ; InitializeGuestSid(void)
0x1800289db  call    ?IsDomainController@@YA_NXZ; IsDomainController(void)
0x1800289e0  mov     rcx, rbx; pSid2
0x1800289e3  test    al, al
0x1800289e5  jnz     short loc_180028A3B
0x1800289e7  mov     [rbp+arg_0], 0
0x1800289ee  mov     [rbp+arg_4], 500h
0x1800289f4  call    cs:__imp_GetSidIdentifierAuthority
0x1800289fa  test    rax, rax
0x1800289fd  jz      short loc_180028A43
0x1800289ff  mov     ecx, [rax]
0x180028a01  sub     ecx, [rbp+arg_0]
0x180028a04  jnz     short loc_180028A10
0x180028a06  movzx   ecx, word ptr [rax+4]
0x180028a0a  movzx   eax, [rbp+arg_4]
0x180028a0e  sub     ecx, eax
0x180028a10  test    ecx, ecx
0x180028a12  jnz     short loc_180028A31
0x180028a14  mov     rdx, cs:?g_pGuestSid@@3PEAXEA; pSid2
0x180028a1b  test    rdx, rdx
0x180028a1e  jz      short loc_180028A2D
0x180028a20  mov     rcx, rbx; pSid1
0x180028a23  call    cs:__imp_EqualPrefixSid
0x180028a29  test    eax, eax
0x180028a2b  jnz     short loc_180028A31
0x180028a2d  xor     edx, edx
0x180028a2f  jmp     short loc_180028A36
0x180028a31  mov     edx, 1
0x180028a36  mov     [r14], edx
0x180028a39  jmp     short loc_180028A43
0x180028a3b  call    ?MQSec_IsGuestSid@@YAHPEAX@Z; MQSec_IsGuestSid(void *)
0x180028a40  mov     [r14], eax
0x180028a43  mov     rcx, rdi; Block
0x180028a46  call    cs:__imp_free
0x180028a4c  nop
0x180028a4d  xor     eax, eax
0x180028a4f  mov     rbx, [rsp+20h+arg_10]
0x180028a54  add     rsp, 20h
0x180028a58  pop     r15
0x180028a5a  pop     r14
0x180028a5c  pop     rdi
0x180028a5d  pop     rsi
0x180028a5e  pop     rbp
0x180028a5f  retn
```
