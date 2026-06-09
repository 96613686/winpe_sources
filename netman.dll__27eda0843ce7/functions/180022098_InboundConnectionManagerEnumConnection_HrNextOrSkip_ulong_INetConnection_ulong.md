# InboundConnectionManagerEnumConnection::HrNextOrSkip(ulong,INetConnection * *,ulong *)

- ea: `0x180022098`
- end: `0x1800223b5`
- name: `?HrNextOrSkip@InboundConnectionManagerEnumConnection@@AEAAJKPEAPEAUINetConnection@@PEAK@Z`
- size: `797`
- prototype: `__int64 __fastcall(InboundConnectionManagerEnumConnection *__hidden this, unsigned int, struct INetConnection **, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022550`
- `0x180022640`

## callees

- `0x180001710`
- `0x180002320`
- `0x18000538c`
- `0x180019c9c`
- `0x180021fb0`
- `0x180022098`
- `0x1800223bc`
- `0x1800306f8`
- `0x180031328`
- `0x180032c3c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18002238f`
- `KERNEL32!LeaveCriticalSection` at `0x18002238f`
- `KERNEL32!EnterCriticalSection` at `0x18002210f`
- `KERNEL32!EnterCriticalSection` at `0x18002210f`
- `RASDLG!RasSrvAllowConnectionsConfig` at `0x18002219d`
- `RASDLG!RasSrvAllowConnectionsConfig` at `0x18002219d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall InboundConnectionManagerEnumConnection::HrNextOrSkip(
        InboundConnectionManagerEnumConnection *this,
        unsigned int a2,
        struct INetConnection **a3,
        unsigned int *a4)
{
  unsigned int *v4; // r14
  char *v9; // rax
  const unsigned __int16 *v10; // rcx
  __int64 v11; // r12
  int active; // esi
  int v13; // ebp
  _DWORD *v14; // r14
  __int64 v15; // rax
  int v16; // eax
  int v17; // ebx
  __int64 v18; // r9
  unsigned int v19; // eax
  void **v20; // rbx
  __int64 v21; // rdi
  PVOID *v22; // rcx
  __int64 v23; // r9
  struct _RTL_CRITICAL_SECTION *lpCriticalSection; // [rsp+28h] [rbp-70h]
  unsigned int v26; // [rsp+38h] [rbp-60h] BYREF

  v4 = a4;
  if ( a2 > 0x1FFFFFFF )
    return 2147942487LL;
  if ( a3 )
    memset_0(a3, 0, 8LL * a2);
  if ( this )
    v9 = (char *)this + 8;
  else
    v9 = 0;
  lpCriticalSection = (struct _RTL_CRITICAL_SECTION *)(v9 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 8));
  v11 = 0;
  if ( !a2 || *((_DWORD *)this + 23) )
    goto LABEL_62;
  active = 0;
  v13 = 0;
  if ( *((_DWORD *)this + 22) )
  {
    *((_DWORD *)this + 22) = 0;
    v26 = 0;
    if ( (int)HrSvcQueryStatus(v10, &v26) >= 0 && v26 == 4 )
    {
      *((_DWORD *)this + 23) = 0;
      v14 = (_DWORD *)((char *)this + 80);
      active = HrRasEnumAllActiveServerConnections((struct _RASSRVCONN **)this + 9, (unsigned int *)this + 20);
      v15 = *((_QWORD *)this + 9);
      if ( active < 0 )
      {
        if ( v15 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v10);
        if ( *v14 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v10);
        active = 0;
        *((_DWORD *)this + 23) = 1;
      }
      else if ( !v15 || !*v14 || !*((_DWORD *)this + 24) )
      {
        v26 = 0;
        v16 = RasSrvAllowConnectionsConfig(&v26);
        v17 = v16;
        if ( v16 > 0 )
          v18 = (unsigned __int16)v16 | 0x80070000;
        else
          v18 = (unsigned int)v16;
        if ( (int)v18 < 0 )
        {
          v10 = (const unsigned __int16 *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_acf5d1b04b8038e035c2505fc051cbfb_Traceguids, v18);
        }
        if ( !v17 && v26 )
          v13 = 1;
        *((_DWORD *)this + 23) = v13 ^ 1;
      }
      v4 = a4;
    }
    else
    {
      *((_DWORD *)this + 23) = 1;
    }
  }
  if ( *((_DWORD *)this + 23) )
    goto LABEL_55;
  v19 = *((_DWORD *)this + 20);
  if ( v19 )
  {
    if ( !v13 )
    {
      v20 = (void **)((char *)this + 72);
      if ( !*((_QWORD *)this + 9) )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v10);
        v19 = *((_DWORD *)this + 20);
      }
      if ( *((_DWORD *)this + 21) >= v19 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v10);
      goto LABEL_50;
    }
  }
  else if ( !v13 )
  {
    goto LABEL_55;
  }
  v20 = (void **)((char *)this + 72);
LABEL_50:
  while ( active >= 0 && (unsigned int)v11 < a2 && (v13 || *((_DWORD *)this + 21) < *((_DWORD *)this + 20)) )
  {
    if ( a3 )
      active = InboundConnectionManagerEnumConnection::HrCreateConfigOrCurrentEnumeratedConnection(this, v13, &a3[v11]);
    v13 = 0;
    v11 = (unsigned int)(v11 + 1);
  }
  if ( *((_DWORD *)this + 21) >= *((_DWORD *)this + 20) )
  {
    if ( active )
      MicrosoftTelemetryAssertTriggeredNoArgs(v10);
    *((_DWORD *)this + 23) = 1;
    MemFree(*v20);
    *v20 = 0;
    *((_DWORD *)this + 20) = 0;
  }
LABEL_55:
  if ( active >= 0 )
  {
LABEL_62:
    v22 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_acf5d1b04b8038e035c2505fc051cbfb_Traceguids,
        (unsigned int)v11);
      v22 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 )
    {
      *v4 = v11;
      v22 = (PVOID *)WPP_GLOBAL_Control;
    }
    active = v11 != a2;
    goto LABEL_68;
  }
  if ( a3 )
  {
    v21 = 0;
    do
    {
      ReleaseObj((struct IUnknown *)a3[v21]);
      a3[v21] = 0;
      v21 = (unsigned int)(v21 + 1);
    }
    while ( (unsigned int)v21 < a2 );
  }
  if ( v4 )
    *v4 = 0;
  v22 = (PVOID *)WPP_GLOBAL_Control;
LABEL_68:
  v23 = 0;
  if ( active != 1 )
    v23 = (unsigned int)active;
  if ( (int)v23 < 0 && v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 1) != 0 )
    WPP_SF_d(v22[2], 15, WPP_acf5d1b04b8038e035c2505fc051cbfb_Traceguids, v23);
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)active;
}

```

## disassembly

```asm
0x180022098  push    rbx
0x18002209a  push    rbp
0x18002209b  push    rsi
0x18002209c  push    rdi
0x18002209d  push    r12
0x18002209f  push    r13
0x1800220a1  push    r14
0x1800220a3  push    r15
0x1800220a5  sub     rsp, 58h
0x1800220a9  mov     rax, cs:__security_cookie
0x1800220b0  xor     rax, rsp
0x1800220b3  mov     [rsp+98h+var_58], rax
0x1800220b8  mov     r14, r9
0x1800220bb  mov     [rsp+98h+var_78], r9
0x1800220c0  mov     r15, r8
0x1800220c3  mov     r13d, edx
0x1800220c6  mov     rdi, rcx
0x1800220c9  cmp     edx, 1FFFFFFFh
0x1800220cf  jbe     short loc_1800220DB
0x1800220d1  mov     eax, 80070057h
0x1800220d6  jmp     loc_180022397
0x1800220db  test    r15, r15
0x1800220de  jz      short loc_1800220F1
0x1800220e0  mov     r8, r13
0x1800220e3  shl     r8, 3; Size
0x1800220e7  xor     edx, edx; Val
0x1800220e9  mov     rcx, r15; void *
0x1800220ec  call    memset_0
0x1800220f1  test    rdi, rdi
0x1800220f4  jz      short loc_1800220FC
0x1800220f6  lea     rax, [rdi+8]
0x1800220fa  jmp     short loc_1800220FE
0x1800220fc  xor     eax, eax
0x1800220fe  mov     [rsp+98h+var_68], rax
0x180022103  add     rax, 8
0x180022107  mov     [rsp+98h+lpCriticalSection], rax
0x18002210c  mov     rcx, rax; lpCriticalSection
0x18002210f  call    cs:__imp_EnterCriticalSection
0x180022115  nop
0x180022116  xor     r12d, r12d
0x180022119  lea     rbx, WPP_GLOBAL_Control
0x180022120  test    r13d, r13d
0x180022123  jz      loc_180022311
0x180022129  cmp     [rdi+5Ch], r12d
0x18002212d  jnz     loc_180022311
0x180022133  xor     esi, esi
0x180022135  xor     ebp, ebp
0x180022137  cmp     [rdi+58h], esi
0x18002213a  jz      loc_180022206
0x180022140  mov     [rdi+58h], esi
0x180022143  mov     [rsp+98h+var_60], esi
0x180022147  lea     rdx, [rsp+98h+var_60]; unsigned int *
0x18002214c  call    ?HrSvcQueryStatus@@YAJPEBGPEAK@Z; HrSvcQueryStatus(ushort const *,ulong *)
0x180022151  test    eax, eax
0x180022153  js      loc_180022244
0x180022159  cmp     [rsp+98h+var_60], 4
0x18002215e  jnz     loc_180022244
0x180022164  mov     [rdi+5Ch], esi
0x180022167  lea     r14, [rdi+50h]
0x18002216b  mov     rdx, r14; unsigned int *
0x18002216e  lea     rcx, [rdi+48h]; struct _RASSRVCONN **
0x180022172  call    ?HrRasEnumAllActiveServerConnections@@YAJPEAPEAU_RASSRVCONN@@PEAK@Z; HrRasEnumAllActiveServerConnections(_RASSRVCONN * *,ulong *)
0x180022177  mov     esi, eax
0x180022179  mov     rax, [rdi+48h]
0x18002217d  test    esi, esi
0x18002217f  js      loc_180022225
0x180022185  test    rax, rax
0x180022188  jz      short loc_180022194
0x18002218a  cmp     [r14], ebp
0x18002218d  jz      short loc_180022194
0x18002218f  cmp     [rdi+60h], ebp
0x180022192  jnz     short loc_180022201
0x180022194  mov     [rsp+98h+var_60], ebp
0x180022198  lea     rcx, [rsp+98h+var_60]
0x18002219d  call    cs:__imp_RasSrvAllowConnectionsConfig
0x1800221a3  mov     ebx, eax
0x1800221a5  test    eax, eax
0x1800221a7  jg      short loc_1800221AE
0x1800221a9  mov     r9d, eax
0x1800221ac  jmp     short loc_1800221B9
0x1800221ae  movzx   r9d, bx
0x1800221b2  or      r9d, 80070000h
0x1800221b9  test    r9d, r9d
0x1800221bc  jns     short loc_1800221EC
0x1800221be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800221c5  lea     rax, WPP_GLOBAL_Control
0x1800221cc  cmp     rcx, rax
0x1800221cf  jz      short loc_1800221EC
0x1800221d1  test    byte ptr [rcx+1Ch], 1
0x1800221d5  jz      short loc_1800221EC
0x1800221d7  mov     edx, 0Dh
0x1800221dc  lea     r8, WPP_acf5d1b04b8038e035c2505fc051cbfb_Traceguids
0x1800221e3  mov     rcx, [rcx+10h]
0x1800221e7  call    WPP_SF_d
0x1800221ec  test    ebx, ebx
0x1800221ee  jnz     short loc_1800221F9
0x1800221f0  cmp     [rsp+98h+var_60], ebp
0x1800221f4  jz      short loc_1800221F9
0x1800221f6  lea     ebp, [rbx+1]
0x1800221f9  mov     eax, ebp
0x1800221fb  xor     eax, 1
0x1800221fe  mov     [rdi+5Ch], eax
0x180022201  mov     r14, [rsp+98h+var_78]
0x180022206  cmp     [rdi+5Ch], r12d
0x18002220a  jnz     loc_1800222CB
0x180022210  mov     eax, [rdi+50h]
0x180022213  test    eax, eax
0x180022215  jnz     short loc_18002224D
0x180022217  test    ebp, ebp
0x180022219  jz      loc_1800222CB
0x18002221f  lea     rbx, [rdi+48h]
0x180022223  jmp     short loc_180022299
0x180022225  test    rax, rax
0x180022228  jz      short loc_18002222F
0x18002222a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002222f  cmp     [r14], ebp
0x180022232  jz      short loc_180022239
0x180022234  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180022239  xor     esi, esi
0x18002223b  mov     dword ptr [rdi+5Ch], 1
0x180022242  jmp     short loc_180022201
0x180022244  mov     dword ptr [rdi+5Ch], 1
0x18002224b  jmp     short loc_180022206
0x18002224d  test    ebp, ebp
0x18002224f  jnz     short loc_18002221F
0x180022251  lea     rbx, [rdi+48h]
0x180022255  cmp     [rbx], r12
0x180022258  jnz     short loc_180022262
0x18002225a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002225f  mov     eax, [rdi+50h]
0x180022262  cmp     [rdi+54h], eax
0x180022265  jb      short loc_180022299
0x180022267  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002226c  jmp     short loc_180022299
0x18002226e  cmp     r12d, r13d
0x180022271  jnb     short loc_18002229D
0x180022273  test    ebp, ebp
0x180022275  jnz     short loc_18002227F
0x180022277  mov     eax, [rdi+50h]
0x18002227a  cmp     [rdi+54h], eax
0x18002227d  jnb     short loc_18002229D
0x18002227f  test    r15, r15
0x180022282  jz      short loc_180022294
0x180022284  lea     r8, [r15+r12*8]; struct INetConnection **
0x180022288  mov     edx, ebp; int
0x18002228a  mov     rcx, rdi; this
0x18002228d  call    ?HrCreateConfigOrCurrentEnumeratedConnection@InboundConnectionManagerEnumConnection@@AEAAJHPEAPEAUINetConnection@@@Z; InboundConnectionManagerEnumConnection::HrCreateConfigOrCurrentEnumeratedConnection(int,INetConnection * *)
0x180022292  mov     esi, eax
0x180022294  xor     ebp, ebp
0x180022296  inc     r12d
0x180022299  test    esi, esi
0x18002229b  jns     short loc_18002226E
0x18002229d  mov     eax, [rdi+50h]
0x1800222a0  cmp     [rdi+54h], eax
0x1800222a3  jb      short loc_1800222CB
0x1800222a5  test    esi, esi
0x1800222a7  jz      short loc_1800222AE
0x1800222a9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800222ae  mov     dword ptr [rdi+5Ch], 1
0x1800222b5  mov     rcx, [rbx]; lpMem
0x1800222b8  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800222bd  mov     qword ptr [rbx], 0
0x1800222c4  mov     dword ptr [rdi+50h], 0
0x1800222cb  test    esi, esi
0x1800222cd  jns     short loc_18002230A
0x1800222cf  test    r15, r15
0x1800222d2  jz      short loc_1800222EE
0x1800222d4  xor     edi, edi
0x1800222d6  mov     rcx, [r15+rdi*8]; struct IUnknown *
0x1800222da  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x1800222df  mov     qword ptr [r15+rdi*8], 0
0x1800222e7  inc     edi
0x1800222e9  cmp     edi, r13d
0x1800222ec  jb      short loc_1800222D6
0x1800222ee  lea     rbx, WPP_GLOBAL_Control
0x1800222f5  test    r14, r14
0x1800222f8  jz      short loc_180022301
0x1800222fa  mov     dword ptr [r14], 0
0x180022301  mov     rcx, cs:WPP_GLOBAL_Control
0x180022308  jmp     short loc_18002235A
0x18002230a  lea     rbx, WPP_GLOBAL_Control
0x180022311  mov     rcx, cs:WPP_GLOBAL_Control
0x180022318  cmp     rcx, rbx
0x18002231b  jz      short loc_180022342
0x18002231d  test    byte ptr [rcx+1Ch], 8
0x180022321  jz      short loc_180022342
0x180022323  mov     edx, 0Eh
0x180022328  mov     r9d, r12d
0x18002232b  lea     r8, WPP_acf5d1b04b8038e035c2505fc051cbfb_Traceguids
0x180022332  mov     rcx, [rcx+10h]
0x180022336  call    WPP_SF_d
0x18002233b  mov     rcx, cs:WPP_GLOBAL_Control
0x180022342  test    r14, r14
0x180022345  jz      short loc_180022351
0x180022347  mov     [r14], r12d
0x18002234a  mov     rcx, cs:WPP_GLOBAL_Control
0x180022351  xor     esi, esi
0x180022353  cmp     r12d, r13d
0x180022356  setnz   sil
0x18002235a  xor     r9d, r9d
0x18002235d  cmp     esi, 1
0x180022360  cmovnz  r9d, esi
0x180022364  test    r9d, r9d
0x180022367  jns     short loc_18002238A
0x180022369  cmp     rcx, rbx
0x18002236c  jz      short loc_18002238A
0x18002236e  test    byte ptr [rcx+1Ch], 1
0x180022372  jz      short loc_18002238A
0x180022374  mov     edx, 0Fh
0x180022379  lea     r8, WPP_acf5d1b04b8038e035c2505fc051cbfb_Traceguids
0x180022380  mov     rcx, [rcx+10h]
0x180022384  call    WPP_SF_d
0x180022389  nop
0x18002238a  mov     rcx, [rsp+98h+lpCriticalSection]; lpCriticalSection
0x18002238f  call    cs:__imp_LeaveCriticalSection
0x180022395  mov     eax, esi
0x180022397  mov     rcx, [rsp+98h+var_58]
0x18002239c  xor     rcx, rsp; StackCookie
0x18002239f  call    __security_check_cookie
0x1800223a4  add     rsp, 58h
0x1800223a8  pop     r15
0x1800223aa  pop     r14
0x1800223ac  pop     r13
0x1800223ae  pop     r12
0x1800223b0  pop     rdi
0x1800223b1  pop     rsi
0x1800223b2  pop     rbp
0x1800223b3  pop     rbx
0x1800223b4  retn
```
