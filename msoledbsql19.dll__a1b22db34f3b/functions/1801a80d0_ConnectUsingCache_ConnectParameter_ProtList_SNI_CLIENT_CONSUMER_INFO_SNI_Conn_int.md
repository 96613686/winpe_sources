# ConnectUsingCache(ConnectParameter *,ProtList *,SNI_CLIENT_CONSUMER_INFO *,SNI_Conn * *,int)

- ea: `0x1801a80d0`
- end: `0x1801a859d`
- name: `?ConnectUsingCache@@YA_NPEAVConnectParameter@@PEAVProtList@@PEAUSNI_CLIENT_CONSUMER_INFO@@PEAPEAVSNI_Conn@@H@Z`
- size: `1229`
- prototype: `bool __usercall@<al>(struct ConnectParameter *@<rcx>, struct ProtList *@<rdx>, struct SNI_CLIENT_CONSUMER_INFO *@<r8>, struct SNI_Conn **@<r9>, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1801a93d0`

## callees

- `0x180001f70`
- `0x180002ef0`
- `0x1800030c0`
- `0x180003d80`
- `0x180152840`
- `0x18015c860`
- `0x18015de80`
- `0x1801a65e1`
- `0x1801a7e30`
- `0x1801a80d0`
- `0x1801a85b0`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1801a8339`
- `KERNEL32!CompareStringW` at `0x1801a8339`
- `KERNEL32!GetTickCount` at `0x1801a81d9`
- `KERNEL32!GetTickCount` at `0x1801a843a`
- `KERNEL32!GetTickCount` at `0x1801a81d9`
- `KERNEL32!GetTickCount` at `0x1801a843a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall ConnectUsingCache(
        wchar_t *a1,
        struct ProtList *a2,
        struct SNI_CLIENT_CONSUMER_INFO *a3,
        struct SNI_Conn **a4,
        int a5)
{
  unsigned int v9; // ebx
  DWORD TickCount; // r12d
  struct ProtElem *v11; // r8
  const WCHAR *v12; // r8
  const wchar_t *v13; // rdx
  DWORD v14; // ecx
  const wchar_t *v15; // rdx
  struct SNI_Conn **cchCount2; // [rsp+28h] [rbp-A90h]
  int v18; // [rsp+30h] [rbp-A88h]
  _QWORD v19[2]; // [rsp+40h] [rbp-A78h] BYREF
  _DWORD v20[2]; // [rsp+50h] [rbp-A68h] BYREF
  __int16 v21; // [rsp+58h] [rbp-A60h]
  _BYTE v22[510]; // [rsp+5Ah] [rbp-A5Eh] BYREF
  __int16 v23; // [rsp+258h] [rbp-860h]
  _BYTE v24[510]; // [rsp+25Ah] [rbp-85Eh] BYREF
  __int16 v25; // [rsp+458h] [rbp-660h]
  _BYTE v26[510]; // [rsp+45Ah] [rbp-65Eh] BYREF
  _BYTE v27[1024]; // [rsp+658h] [rbp-460h] BYREF
  __int64 v28; // [rsp+A58h] [rbp-60h]

  v19[0] = -1;
  v9 = a5;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_180266FC8[0] )
  {
    v18 = a5;
    cchCount2 = a4;
    bidScopeEnterW(v19, off_180266FC8[0], a1, a2);
  }
  memset_0(v22, 0, sizeof(v22));
  memset_0(v24, 0, sizeof(v24));
  memset_0(v26, 0, 0x5FEu);
  memset_0(v27, 0, sizeof(v27));
  wcscpy((wchar_t *)v20, L"\b");
  v20[1] = 8;
  v21 = 0;
  v23 = 0;
  v25 = 0;
  v28 = 0;
  TickCount = GetTickCount();
  if ( ProtElem::Init((ProtElem *)v20, a1, a1 + 256) )
  {
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_180265F90[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, char *, __int64, wchar_t *, _QWORD, struct SNI_Conn **, int))off_180248050[0])(
        bidID,
        off_1802627C0[0],
        622592,
        off_180265F90[0],
        0,
        cchCount2,
        v18);
LABEL_46:
    _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)v19);
    return 0;
  }
  if ( !(unsigned int)LastConnectCache::GetEntry(a1 + 1035, (const wchar_t *)v20, v11) )
  {
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_180265F98[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, char *, __int64, wchar_t *, _QWORD, struct SNI_Conn **, int))off_180248050[0])(
        bidID,
        off_1802627C8[0],
        631808,
        off_180265F98[0],
        0,
        cchCount2,
        v18);
    goto LABEL_46;
  }
  if ( a1[768] )
  {
    switch ( v20[0] )
    {
      case 1:
        v12 = L"np";
        break;
      case 3:
        v12 = L"lpc";
        break;
      case 6:
        v12 = L"tcp";
        break;
      default:
LABEL_24:
        if ( (bidGblFlags & 0x20002) == 0x20002 && off_180265FA0[0] && bidID != -1 )
          ((void (__fastcall *)(__int64, char *, __int64, wchar_t *, _QWORD, struct SNI_Conn **, int))off_180248050[0])(
            bidID,
            off_1802627D0[0],
            674816,
            off_180265FA0[0],
            0,
            cchCount2,
            v18);
        goto LABEL_46;
    }
    if ( CompareStringW(0x800u, 0x20000u, v12, -1, a1 + 768, -1) != 2 )
      goto LABEL_24;
  }
  else if ( !ProtList::Find(a2, v20[0]) )
  {
    LastConnectCache::RemoveEntry(a1 + 1035, v13);
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_180265FA8[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, char *, __int64, wchar_t *, _QWORD, struct SNI_Conn **, int))off_180248050[0])(
        bidID,
        off_1802627D8[0],
        684032,
        off_180265FA8[0],
        0,
        cchCount2,
        v18);
    goto LABEL_46;
  }
  if ( a5 != -1 )
  {
    v14 = TickCount + a5 - GetTickCount();
    v9 = -2;
    if ( v14 != -1 )
      v9 = v14;
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_180265FB0[0] )
      bidTraceW(off_1802627E0[0], 700416, off_180265FB0[0], v9);
  }
  if ( Connect((struct ConnectParameter *)a1, a3, (struct ProtElem *)v20, a4, v9) )
  {
    LastConnectCache::RemoveEntry(a1 + 1035, v15);
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_180265FB8[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, char *, __int64, wchar_t *, _QWORD, struct SNI_Conn **, int))off_180248050[0])(
        bidID,
        off_1802627E8[0],
        707584,
        off_180265FB8[0],
        0,
        cchCount2,
        v18);
    goto LABEL_46;
  }
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_180265FC0[0] && bidID != -1 )
    ((void (__fastcall *)(__int64, char *, __int64, wchar_t *, _QWORD, struct SNI_Conn **, int))off_180248050[0])(
      bidID,
      off_1802627F0[0],
      712704,
      off_180265FC0[0],
      0,
      cchCount2,
      v18);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)v19);
  return 1;
}

```

## disassembly

```asm
0x1801a80d0  push    rbx
0x1801a80d2  push    rbp
0x1801a80d3  push    rsi
0x1801a80d4  push    rdi
0x1801a80d5  push    r12
0x1801a80d7  push    r13
0x1801a80d9  push    r14
0x1801a80db  push    r15
0x1801a80dd  sub     rsp, 0A78h
0x1801a80e4  mov     rax, cs:__security_cookie
0x1801a80eb  xor     rax, rsp
0x1801a80ee  mov     [rsp+0AB8h+var_58], rax
0x1801a80f6  mov     r15, r9
0x1801a80f9  mov     r14, r8
0x1801a80fc  mov     rbp, rdx
0x1801a80ff  mov     rdi, rcx
0x1801a8102  mov     [rsp+0AB8h+var_A78], 0FFFFFFFFFFFFFFFFh
0x1801a810b  mov     eax, cs:_bidGblFlags
0x1801a8111  and     eax, 20004h
0x1801a8116  mov     ebx, [rsp+0AB8h+arg_20]
0x1801a811d  cmp     eax, 20004h
0x1801a8122  jnz     short loc_1801A8155
0x1801a8124  mov     rax, cs:off_180266FC8; "<ConnectUsingCache|API|SNI> pConnectPar"...
0x1801a812b  test    rax, rax
0x1801a812e  jz      short loc_1801A8155
0x1801a8130  mov     [rsp+0AB8h+var_A88], ebx
0x1801a8134  mov     qword ptr [rsp+0AB8h+cchCount2], r9
0x1801a8139  mov     [rsp+0AB8h+lpString2], r8
0x1801a813e  mov     r9, rdx
0x1801a8141  mov     r8, rcx
0x1801a8144  mov     rdx, cs:off_180266FC8; "<ConnectUsingCache|API|SNI> pConnectPar"...
0x1801a814b  lea     rcx, [rsp+0AB8h+var_A78]
0x1801a8150  call    _bidScopeEnterW
0x1801a8155  xor     edx, edx; Val
0x1801a8157  mov     r8d, 1FEh; Size
0x1801a815d  lea     rcx, [rsp+0AB8h+var_A5E]; void *
0x1801a8162  call    memset_0
0x1801a8167  xor     edx, edx; Val
0x1801a8169  mov     r8d, 1FEh; Size
0x1801a816f  lea     rcx, [rsp+0AB8h+var_85E]; void *
0x1801a8177  call    memset_0
0x1801a817c  xor     edx, edx; Val
0x1801a817e  mov     r8d, 5FEh; Size
0x1801a8184  lea     rcx, [rsp+0AB8h+var_65E]; void *
0x1801a818c  call    memset_0
0x1801a8191  xor     edx, edx; Val
0x1801a8193  mov     r8d, 400h; Size
0x1801a8199  lea     rcx, [rsp+0AB8h+var_460]; void *
0x1801a81a1  call    memset_0
0x1801a81a6  mov     dword ptr [rsp+0AB8h+var_A68], 8
0x1801a81ae  mov     dword ptr [rsp+0AB8h+var_A68+4], 8
0x1801a81b6  xor     r13d, r13d
0x1801a81b9  mov     [rsp+0AB8h+var_A60], r13w
0x1801a81bf  mov     [rsp+0AB8h+var_860], r13w
0x1801a81c8  mov     [rsp+0AB8h+var_660], r13w
0x1801a81d1  mov     [rsp+0AB8h+var_60], r13
0x1801a81d9  call    cs:__imp_GetTickCount
0x1801a81df  mov     r12d, eax
0x1801a81e2  lea     r8, [rdi+200h]; wchar_t *
0x1801a81e9  mov     rdx, rdi; wchar_t *
0x1801a81ec  lea     rcx, [rsp+0AB8h+var_A68]; this
0x1801a81f1  call    ?Init@ProtElem@@QEAAKQEB_W0@Z; ProtElem::Init(wchar_t const * const,wchar_t const * const)
0x1801a81f6  test    eax, eax
0x1801a81f8  jz      short loc_1801A8262
0x1801a81fa  mov     eax, cs:_bidGblFlags
0x1801a8200  and     eax, 20002h
0x1801a8205  cmp     eax, 20002h
0x1801a820a  jnz     short loc_1801A8250
0x1801a820c  mov     rax, cs:off_180265F90; "<ConnectUsingCache|RET|SNI> false\n"
0x1801a8213  test    rax, rax
0x1801a8216  jz      short loc_1801A8250
0x1801a8218  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x1801a8220  jz      short loc_1801A8250
0x1801a8222  mov     rax, cs:off_180248050
0x1801a8229  mov     [rsp+0AB8h+lpString2], r13
0x1801a822e  mov     r9, cs:off_180265F90; "<ConnectUsingCache|RET|SNI> false\n"
0x1801a8235  mov     r8d, 98000h
0x1801a823b  mov     rdx, cs:off_1802627C0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801a8242  mov     rcx, cs:_bidID
0x1801a8249  call    cs:__guard_dispatch_icall_fptr
0x1801a824f  nop
0x1801a8250  lea     rcx, [rsp+0AB8h+var_A78]; this
0x1801a8255  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x1801a825a  nop
0x1801a825b  xor     al, al
0x1801a825d  jmp     loc_1801A8579
0x1801a8262  lea     rdx, [rsp+0AB8h+var_A68]; wchar_t *
0x1801a8267  lea     rcx, [rdi+816h]; lpString2
0x1801a826e  call    ?GetEntry@LastConnectCache@@YAHPEB_WPEAVProtElem@@@Z; LastConnectCache::GetEntry(wchar_t const *,ProtElem *)
0x1801a8273  test    eax, eax
0x1801a8275  jnz     short loc_1801A82DF
0x1801a8277  mov     eax, cs:_bidGblFlags
0x1801a827d  and     eax, 20002h
0x1801a8282  cmp     eax, 20002h
0x1801a8287  jnz     short loc_1801A82CD
0x1801a8289  mov     rax, cs:off_180265F98; "<ConnectUsingCache|RET|SNI> false\n"
0x1801a8290  test    rax, rax
0x1801a8293  jz      short loc_1801A82CD
0x1801a8295  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x1801a829d  jz      short loc_1801A82CD
0x1801a829f  mov     rax, cs:off_180248050
0x1801a82a6  mov     [rsp+0AB8h+lpString2], r13
0x1801a82ab  mov     r9, cs:off_180265F98; "<ConnectUsingCache|RET|SNI> false\n"
0x1801a82b2  mov     r8d, 9A400h
0x1801a82b8  mov     rdx, cs:off_1802627C8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801a82bf  mov     rcx, cs:_bidID
0x1801a82c6  call    cs:__guard_dispatch_icall_fptr
0x1801a82cc  nop
0x1801a82cd  lea     rcx, [rsp+0AB8h+var_A78]; this
0x1801a82d2  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x1801a82d7  nop
0x1801a82d8  xor     al, al
0x1801a82da  jmp     loc_1801A8579
0x1801a82df  lea     rdx, [rdi+600h]
0x1801a82e6  cmp     [rdx], r13w
0x1801a82ea  jz      loc_1801A83B0
0x1801a82f0  mov     ecx, dword ptr [rsp+0AB8h+var_A68]
0x1801a82f4  sub     ecx, 1
0x1801a82f7  jz      short loc_1801A8315
0x1801a82f9  sub     ecx, 2
0x1801a82fc  jz      short loc_1801A830C
0x1801a82fe  cmp     ecx, 3
0x1801a8301  jnz     short loc_1801A8348
0x1801a8303  lea     r8, aTcp_1; "tcp"
0x1801a830a  jmp     short loc_1801A831C
0x1801a830c  lea     r8, aLpc; "lpc"
0x1801a8313  jmp     short loc_1801A831C
0x1801a8315  lea     r8, aNp; "np"
0x1801a831c  mov     [rsp+0AB8h+cchCount2], 0FFFFFFFFh; cchCount2
0x1801a8324  mov     [rsp+0AB8h+lpString2], rdx; lpString2
0x1801a8329  mov     edx, 20000h; dwCmpFlags
0x1801a832e  mov     ecx, 800h; Locale
0x1801a8333  mov     r9d, 0FFFFFFFFh; cchCount1
0x1801a8339  call    cs:__imp_CompareStringW
0x1801a833f  cmp     eax, 2
0x1801a8342  jz      loc_1801A8435
0x1801a8348  mov     eax, cs:_bidGblFlags
0x1801a834e  and     eax, 20002h
0x1801a8353  cmp     eax, 20002h
0x1801a8358  jnz     short loc_1801A839E
0x1801a835a  mov     rax, cs:off_180265FA0; "<ConnectUsingCache|RET|SNI> false\n"
0x1801a8361  test    rax, rax
0x1801a8364  jz      short loc_1801A839E
0x1801a8366  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x1801a836e  jz      short loc_1801A839E
0x1801a8370  mov     rax, cs:off_180248050
0x1801a8377  mov     [rsp+0AB8h+lpString2], r13
0x1801a837c  mov     r9, cs:off_180265FA0; "<ConnectUsingCache|RET|SNI> false\n"
0x1801a8383  mov     r8d, 0A4C00h
0x1801a8389  mov     rdx, cs:off_1802627D0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801a8390  mov     rcx, cs:_bidID
0x1801a8397  call    cs:__guard_dispatch_icall_fptr
0x1801a839d  nop
0x1801a839e  lea     rcx, [rsp+0AB8h+var_A78]; this
0x1801a83a3  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x1801a83a8  nop
0x1801a83a9  xor     al, al
0x1801a83ab  jmp     loc_1801A8579
0x1801a83b0  mov     edx, dword ptr [rsp+0AB8h+var_A68]
0x1801a83b4  mov     rcx, rbp
0x1801a83b7  call    ?Find@ProtList@@QEAAPEAVProtElem@@W4ProviderNum@@@Z; ProtList::Find(ProviderNum)
0x1801a83bc  test    rax, rax
0x1801a83bf  jnz     short loc_1801A8435
0x1801a83c1  lea     rcx, [rdi+816h]; this
0x1801a83c8  call    ?RemoveEntry@LastConnectCache@@YAXPEB_W@Z; LastConnectCache::RemoveEntry(wchar_t const *)
0x1801a83cd  mov     eax, cs:_bidGblFlags
0x1801a83d3  and     eax, 20002h
0x1801a83d8  cmp     eax, 20002h
0x1801a83dd  jnz     short loc_1801A8423
0x1801a83df  mov     rax, cs:off_180265FA8; "<ConnectUsingCache|RET|SNI> false\n"
0x1801a83e6  test    rax, rax
0x1801a83e9  jz      short loc_1801A8423
0x1801a83eb  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x1801a83f3  jz      short loc_1801A8423
0x1801a83f5  mov     rax, cs:off_180248050
0x1801a83fc  mov     [rsp+0AB8h+lpString2], r13
0x1801a8401  mov     r9, cs:off_180265FA8; "<ConnectUsingCache|RET|SNI> false\n"
0x1801a8408  mov     r8d, 0A7000h
0x1801a840e  mov     rdx, cs:off_1802627D8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801a8415  mov     rcx, cs:_bidID
0x1801a841c  call    cs:__guard_dispatch_icall_fptr
0x1801a8422  nop
0x1801a8423  lea     rcx, [rsp+0AB8h+var_A78]; this
0x1801a8428  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x1801a842d  nop
0x1801a842e  xor     al, al
0x1801a8430  jmp     loc_1801A8579
0x1801a8435  cmp     ebx, 0FFFFFFFFh
0x1801a8438  jz      short loc_1801A848A
0x1801a843a  call    cs:__imp_GetTickCount
0x1801a8440  lea     ecx, [r12+rbx]
0x1801a8444  sub     ecx, eax
0x1801a8446  mov     ebx, 0FFFFFFFEh
0x1801a844b  cmp     ecx, 0FFFFFFFFh
0x1801a844e  cmovnz  ebx, ecx
0x1801a8451  mov     eax, cs:_bidGblFlags
0x1801a8457  and     eax, 20002h
0x1801a845c  cmp     eax, 20002h
0x1801a8461  jnz     short loc_1801A848A
0x1801a8463  mov     rax, cs:off_180265FB0; "<ConnectUsingCache|SNI> timeout: %d\n"
0x1801a846a  test    rax, rax
0x1801a846d  jz      short loc_1801A848A
0x1801a846f  mov     r9d, ebx
0x1801a8472  mov     r8, cs:off_180265FB0; "<ConnectUsingCache|SNI> timeout: %d\n"
0x1801a8479  mov     edx, 0AB000h
0x1801a847e  mov     rcx, cs:off_1802627E0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801a8485  call    _bidTraceW
0x1801a848a  mov     dword ptr [rsp+0AB8h+lpString2], ebx; int
0x1801a848e  mov     r9, r15; struct SNI_Conn **
0x1801a8491  lea     r8, [rsp+0AB8h+var_A68]; struct ProtElem *
0x1801a8496  mov     rdx, r14; struct SNI_CLIENT_CONSUMER_INFO *
0x1801a8499  mov     rcx, rdi; struct ConnectParameter *
0x1801a849c  call    ?Connect@@YAKPEAVConnectParameter@@PEAUSNI_CLIENT_CONSUMER_INFO@@PEAVProtElem@@PEAPEAVSNI_Conn@@H@Z; Connect(ConnectParameter *,SNI_CLIENT_CONSUMER_INFO *,ProtElem *,SNI_Conn * *,int)
0x1801a84a1  test    eax, eax
0x1801a84a3  jz      short loc_1801A8516
0x1801a84a5  lea     rcx, [rdi+816h]; this
0x1801a84ac  call    ?RemoveEntry@LastConnectCache@@YAXPEB_W@Z; LastConnectCache::RemoveEntry(wchar_t const *)
0x1801a84b1  mov     eax, cs:_bidGblFlags
0x1801a84b7  and     eax, 20002h
0x1801a84bc  cmp     eax, 20002h
0x1801a84c1  jnz     short loc_1801A8507
0x1801a84c3  mov     rax, cs:off_180265FB8; "<ConnectUsingCache|RET|SNI> false\n"
0x1801a84ca  test    rax, rax
0x1801a84cd  jz      short loc_1801A8507
0x1801a84cf  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x1801a84d7  jz      short loc_1801A8507
0x1801a84d9  mov     rax, cs:off_180248050
0x1801a84e0  mov     [rsp+0AB8h+lpString2], r13
0x1801a84e5  mov     r9, cs:off_180265FB8; "<ConnectUsingCache|RET|SNI> false\n"
0x1801a84ec  mov     r8d, 0ACC00h
0x1801a84f2  mov     rdx, cs:off_1802627E8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801a84f9  mov     rcx, cs:_bidID
0x1801a8500  call    cs:__guard_dispatch_icall_fptr
0x1801a8506  nop
0x1801a8507  lea     rcx, [rsp+0AB8h+var_A78]; this
0x1801a850c  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x1801a8511  nop
0x1801a8512  xor     al, al
0x1801a8514  jmp     short loc_1801A8579
0x1801a8516  mov     eax, cs:_bidGblFlags
0x1801a851c  and     eax, 20002h
0x1801a8521  cmp     eax, 20002h
0x1801a8526  jnz     short loc_1801A856C
0x1801a8528  mov     rax, cs:off_180265FC0; "<ConnectUsingCache|RET|SNI> true\n"
0x1801a852f  test    rax, rax
0x1801a8532  jz      short loc_1801A856C
0x1801a8534  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x1801a853c  jz      short loc_1801A856C
0x1801a853e  mov     rax, cs:off_180248050
0x1801a8545  mov     [rsp+0AB8h+lpString2], r13
0x1801a854a  mov     r9, cs:off_180265FC0; "<ConnectUsingCache|RET|SNI> true\n"
0x1801a8551  mov     r8d, 0AE000h
0x1801a8557  mov     rdx, cs:off_1802627F0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801a855e  mov     rcx, cs:_bidID
0x1801a8565  call    cs:__guard_dispatch_icall_fptr
0x1801a856b  nop
0x1801a856c  lea     rcx, [rsp+0AB8h+var_A78]; this
0x1801a8571  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x1801a8576  nop
0x1801a8577  mov     al, 1
0x1801a8579  mov     rcx, [rsp+0AB8h+var_58]
0x1801a8581  xor     rcx, rsp; StackCookie
0x1801a8584  call    __security_check_cookie
0x1801a8589  add     rsp, 0A78h
0x1801a8590  pop     r15
0x1801a8592  pop     r14
0x1801a8594  pop     r13
0x1801a8596  pop     r12
0x1801a8598  pop     rdi
0x1801a8599  pop     rsi
0x1801a859a  pop     rbp
0x1801a859b  pop     rbx
0x1801a859c  retn
```
