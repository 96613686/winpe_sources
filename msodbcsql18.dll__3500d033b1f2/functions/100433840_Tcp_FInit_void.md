# Tcp::FInit(void)

- ea: `0x100433840`
- end: `0x100433a8e`
- name: `?FInit@Tcp@@EEAAKXZ`
- size: `590`
- prototype: `unsigned int __fastcall(Tcp *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x100413d10`
- `0x100433840`
- `0x10043b1d0`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x100433948`
- `KERNEL32!CreateEventW` at `0x100433948`
- `KERNEL32!GetLastError` at `0x100433969`
- `KERNEL32!GetLastError` at `0x100433969`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Tcp::FInit(struct CCriticalSectionNT_SNI **this)
{
  DWORD LastError; // ebx
  __int64 v3; // rax
  struct CCriticalSectionNT_SNI *v4; // rax
  struct CCriticalSectionNT_SNI *v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v9; // [rsp+68h] [rbp+10h] BYREF

  v9 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7D00[0] )
    bidScopeEnterW(&v9, off_1005E7D00[0], *((unsigned int *)this + 11));
  LastError = SNI::detail::Transport::Initialize((SNI::detail::Transport *)this);
  if ( !LastError && Tcp::s_fAutoTuning )
  {
    v3 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)gpmo + 88LL))(gpmo, 32);
    this[40] = (struct CCriticalSectionNT_SNI *)v3;
    if ( !v3 )
    {
LABEL_7:
      LastError = 14;
      goto LABEL_20;
    }
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E57E8[0] )
      bidTraceW(0, 2107392, off_1005E57E8[0], *((unsigned int *)this[4] + 12));
    v4 = this[40];
    *(_OWORD *)v4 = 0;
    *((_OWORD *)v4 + 1) = 0;
    *((_QWORD *)this[40] + 3) = CreateEventW(0, 1, 1, 0);
    v5 = this[40];
    v6 = *((_QWORD *)v5 + 3);
    if ( v6 )
    {
      *((_QWORD *)v5 + 3) = v6 | 1;
      v7 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)gpmo + 88LL))(gpmo, 32);
      this[41] = (struct CCriticalSectionNT_SNI *)v7;
      if ( !v7 )
        goto LABEL_7;
      *(_QWORD *)(v7 + 16) = this[40];
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E57F8[0] )
        bidTraceW(0, 2143232, off_1005E57F8[0], *((unsigned int *)this[4] + 12));
      LastError = CCriticalSectionNT_SNI::Initialize(this + 39);
    }
    else
    {
      LastError = GetLastError();
      if ( (bidGblFlags & 2) != 0 && off_1005E57F0[0] )
        bidTraceW(0, 2123776, off_1005E57F0[0], LastError);
    }
  }
LABEL_20:
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E5800[0] )
    bidTraceW(0, 2153472, off_1005E5800[0], LastError);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v9);
  return LastError;
}

```

## disassembly

```asm
0x100433840  mov     r11, rsp
0x100433843  push    rdi
0x100433844  sub     rsp, 50h
0x100433848  mov     qword ptr [r11-18h], 0FFFFFFFFFFFFFFFEh
0x100433850  mov     [r11+8], rbx
0x100433854  mov     [r11+18h], rsi
0x100433858  mov     rdi, rcx
0x10043385b  or      qword ptr [r11+10h], 0FFFFFFFFFFFFFFFFh
0x100433860  mov     eax, cs:_bidGblFlags
0x100433866  mov     ecx, 20004h
0x10043386b  and     eax, ecx
0x10043386d  cmp     eax, ecx
0x10043386f  jnz     short loc_100433891
0x100433871  mov     rax, cs:off_1005E7D00; "<Tcp::FInit|API|SNI> %u#\n"
0x100433878  test    rax, rax
0x10043387b  jz      short loc_100433891
0x10043387d  mov     r8d, [rdi+2Ch]
0x100433881  mov     rdx, cs:off_1005E7D00; "<Tcp::FInit|API|SNI> %u#\n"
0x100433888  lea     rcx, [r11+10h]
0x10043388c  call    _bidScopeEnterW
0x100433891  mov     rcx, rdi; this
0x100433894  call    ?Initialize@Transport@detail@SNI@@QEAAKXZ; SNI::detail::Transport::Initialize(void)
0x100433899  mov     ebx, eax
0x10043389b  mov     esi, 20002h
0x1004338a0  test    eax, eax
0x1004338a2  jnz     loc_100433A43
0x1004338a8  cmp     cs:?s_fAutoTuning@Tcp@@2HA, eax; int Tcp::s_fAutoTuning
0x1004338ae  jz      loc_100433A43
0x1004338b4  mov     rcx, cs:?gpmo@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * gpmo
0x1004338bb  mov     rax, [rcx]
0x1004338be  mov     ebx, 20h ; ' '
0x1004338c3  mov     edx, ebx
0x1004338c5  mov     rax, [rax+58h]
0x1004338c9  call    cs:__guard_dispatch_icall_fptr
0x1004338cf  mov     [rdi+140h], rax
0x1004338d6  test    rax, rax
0x1004338d9  jnz     short loc_1004338E5
0x1004338db  mov     ebx, 0Eh
0x1004338e0  jmp     loc_100433A43
0x1004338e5  mov     eax, cs:_bidGblFlags
0x1004338eb  and     eax, esi
0x1004338ed  cmp     eax, esi
0x1004338ef  jnz     short loc_10043392B
0x1004338f1  mov     rax, cs:off_1005E57E8; "<Tcp::FInit|API|SNI> m_pOvSendNotificat"...
0x1004338f8  test    rax, rax
0x1004338fb  jz      short loc_10043392B
0x1004338fd  mov     rcx, [rdi+20h]
0x100433901  mov     rax, [rdi+140h]
0x100433908  mov     [rsp+58h+var_30], rax
0x10043390d  mov     eax, [rdi+2Ch]
0x100433910  mov     [rsp+58h+var_38], eax
0x100433914  mov     r9d, [rcx+30h]
0x100433918  mov     r8, cs:off_1005E57E8; "<Tcp::FInit|API|SNI> m_pOvSendNotificat"...
0x10043391f  mov     edx, 202800h
0x100433924  xor     ecx, ecx
0x100433926  call    _bidTraceW
0x10043392b  xorps   xmm0, xmm0
0x10043392e  mov     rax, [rdi+140h]
0x100433935  movups  xmmword ptr [rax], xmm0
0x100433938  movups  xmmword ptr [rax+10h], xmm0
0x10043393c  xor     r9d, r9d; lpName
0x10043393f  lea     edx, [r9+1]; bManualReset
0x100433943  xor     ecx, ecx; lpEventAttributes
0x100433945  mov     r8d, edx; bInitialState
0x100433948  call    cs:__imp_CreateEventW
0x10043394e  mov     rcx, [rdi+140h]
0x100433955  mov     [rcx+18h], rax
0x100433959  mov     rcx, [rdi+140h]
0x100433960  mov     rax, [rcx+18h]
0x100433964  test    rax, rax
0x100433967  jnz     short loc_1004339A9
0x100433969  call    cs:__imp_GetLastError
0x10043396f  mov     ebx, eax
0x100433971  test    byte ptr cs:_bidGblFlags, 2
0x100433978  jz      loc_100433A43
0x10043397e  mov     rax, cs:off_1005E57F0; "<Tcp::FInit|ERR|SNI> m_pOvSendNotificat"...
0x100433985  test    rax, rax
0x100433988  jz      loc_100433A43
0x10043398e  mov     r9d, ebx
0x100433991  mov     r8, cs:off_1005E57F0; "<Tcp::FInit|ERR|SNI> m_pOvSendNotificat"...
0x100433998  mov     edx, 206800h
0x10043399d  xor     ecx, ecx
0x10043399f  call    _bidTraceW
0x1004339a4  jmp     loc_100433A43
0x1004339a9  or      rax, 1
0x1004339ad  mov     [rcx+18h], rax
0x1004339b1  mov     rcx, cs:?gpmo@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * gpmo
0x1004339b8  mov     rax, [rcx]
0x1004339bb  mov     rdx, rbx
0x1004339be  mov     rax, [rax+58h]
0x1004339c2  call    cs:__guard_dispatch_icall_fptr
0x1004339c8  mov     rcx, rax
0x1004339cb  mov     [rdi+148h], rax
0x1004339d2  test    rax, rax
0x1004339d5  jz      loc_1004338DB
0x1004339db  mov     rax, [rdi+140h]
0x1004339e2  mov     [rcx+10h], rax
0x1004339e6  mov     eax, cs:_bidGblFlags
0x1004339ec  and     eax, esi
0x1004339ee  cmp     eax, esi
0x1004339f0  jnz     short loc_100433A35
0x1004339f2  mov     rax, cs:off_1005E57F8; "<Tcp::FInit|API|SNI> m_pOvSendNotificat"...
0x1004339f9  test    rax, rax
0x1004339fc  jz      short loc_100433A35
0x1004339fe  mov     rcx, [rdi+140h]
0x100433a05  mov     rdx, [rdi+20h]
0x100433a09  mov     rax, [rcx+18h]
0x100433a0d  mov     [rsp+58h+var_28], rax
0x100433a12  mov     [rsp+58h+var_30], rcx
0x100433a17  mov     eax, [rdi+2Ch]
0x100433a1a  mov     [rsp+58h+var_38], eax
0x100433a1e  mov     r9d, [rdx+30h]
0x100433a22  mov     r8, cs:off_1005E57F8; "<Tcp::FInit|API|SNI> m_pOvSendNotificat"...
0x100433a29  mov     edx, 20B400h
0x100433a2e  xor     ecx, ecx
0x100433a30  call    _bidTraceW
0x100433a35  lea     rcx, [rdi+138h]; struct CCriticalSectionNT_SNI **
0x100433a3c  call    ?Initialize@CCriticalSectionNT_SNI@@SAKPEAPEAV1@@Z; CCriticalSectionNT_SNI::Initialize(CCriticalSectionNT_SNI * *)
0x100433a41  mov     ebx, eax
0x100433a43  mov     eax, cs:_bidGblFlags
0x100433a49  and     eax, esi
0x100433a4b  cmp     eax, esi
0x100433a4d  jnz     short loc_100433A72
0x100433a4f  mov     rax, cs:off_1005E5800; "<Tcp::FInit|RET|SNI> %d{WINERR}\n"
0x100433a56  test    rax, rax
0x100433a59  jz      short loc_100433A72
0x100433a5b  mov     r9d, ebx
0x100433a5e  mov     r8, cs:off_1005E5800; "<Tcp::FInit|RET|SNI> %d{WINERR}\n"
0x100433a65  mov     edx, 20DC00h
0x100433a6a  xor     ecx, ecx
0x100433a6c  call    _bidTraceW
0x100433a71  nop
0x100433a72  lea     rcx, [rsp+58h+arg_8]; this
0x100433a77  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x100433a7c  mov     eax, ebx
0x100433a7e  mov     rbx, [rsp+58h+arg_0]
0x100433a83  mov     rsi, [rsp+58h+arg_10]
0x100433a88  add     rsp, 50h
0x100433a8c  pop     rdi
0x100433a8d  retn
```
