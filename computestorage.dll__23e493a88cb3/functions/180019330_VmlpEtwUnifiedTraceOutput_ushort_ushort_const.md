# VmlpEtwUnifiedTraceOutput(ushort,ushort const *)

- ea: `0x180019330`
- end: `0x1800196a0`
- name: `?VmlpEtwUnifiedTraceOutput@@YAXGPEBG@Z`
- size: `880`
- prototype: `void __fastcall(unsigned __int16, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180002690`
- `0x180002b74`
- `0x180002bac`
- `0x1800032b8`
- `0x1800191c8`
- `0x180019330`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001960e`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001965d`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001960e`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001965d`

## pseudocode

```c
void __fastcall VmlpEtwUnifiedTraceOutput(unsigned __int16 a1, const unsigned __int16 *a2)
{
  struct _VML_ETW_TRACE *v2; // rsi
  unsigned __int64 v3; // r14
  const unsigned __int16 *v5; // rax
  __int64 v6; // rdx
  signed int v7; // ecx
  __int64 v8; // rbp
  __int64 v9; // r13
  struct VmlEventDataForStackTrace *v10; // rax
  struct VmlEventDataForStackTrace *v11; // rbx
  struct _EVENT_DATA_DESCRIPTOR *v12; // rdi
  __int16 v13; // r12
  ULONG v14; // eax
  __int64 v15; // r15
  void **v16; // rbp
  _QWORD *ThreadLocalStoragePointer; // rax
  __int64 v18; // rdx
  const unsigned __int16 *v19; // r9
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // rdx
  const unsigned __int16 *v24; // r8
  __int64 v25; // rcx
  int v26; // r10d
  int v27; // r10d
  int v28; // ecx
  int v29; // edx
  __int64 v30; // r8
  unsigned int v31; // edx
  unsigned int v32; // eax
  ULONG v33; // r14d
  bool v34; // cf
  const EVENT_DESCRIPTOR *EventDescriptor; // [rsp+20h] [rbp-C8h]
  unsigned int v36; // [rsp+28h] [rbp-C0h] BYREF
  unsigned int v37; // [rsp+2Ch] [rbp-BCh] BYREF
  char v38; // [rsp+30h] [rbp-B8h] BYREF

  v2 = g_VmlEtwTrace;
  v3 = a1;
  if ( g_VmlEtwTrace )
  {
    if ( a2 )
    {
      v5 = a2;
      v6 = 1024;
      do
      {
        if ( !*v5 )
          break;
        ++v5;
        --v6;
      }
      while ( v6 );
      v7 = v6 == 0 ? 0x80070057 : 0;
      if ( v6 )
      {
        v8 = (2 * (1024 - v6)) & -(__int64)(v6 != 0);
        goto LABEL_10;
      }
    }
    else
    {
      v7 = -2147024809;
    }
    LODWORD(v8) = 0;
LABEL_10:
    if ( v7 < 0 )
      return;
    v9 = (unsigned __int16)v3 >> 14;
    EventDescriptor = (const EVENT_DESCRIPTOR *)*((_QWORD *)g_VmlEtwTrace
                                                + 128 * ((v3 >> 5) & 0x1F)
                                                + 4 * (v3 & 0x1F)
                                                + (unsigned int)v9
                                                + 39);
    if ( (v3 & 0x800) != 0 )
    {
      v10 = (struct VmlEventDataForStackTrace *)operator new(0x8D0u, (const struct std::nothrow_t *)&std::nothrow);
      v2 = g_VmlEtwTrace;
      v11 = v10;
      if ( v10 )
      {
        v12 = (struct _EVENT_DATA_DESCRIPTOR *)v10;
        goto LABEL_16;
      }
    }
    else
    {
      v11 = 0;
    }
    v10 = 0;
    v12 = (struct _EVENT_DATA_DESCRIPTOR *)&v38;
LABEL_16:
    v13 = v3 & 0xF7FF;
    if ( v10 )
      v13 = v3;
    memset_0(&v12[1], 0, 0x50u);
    v14 = v8 + 2;
    v12->Ptr = (ULONGLONG)a2;
    v15 = (unsigned int)tls_index;
    v16 = 0;
    v12->Size = v14;
    ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
    v12->Reserved = 0;
    v18 = ThreadLocalStoragePointer[v15];
    v19 = (const unsigned __int16 *)(v18 + 2812);
    v20 = -1;
    v21 = -1;
    do
      ++v21;
    while ( v19[v21] );
    v22 = v18 + 2608;
    v23 = -1;
    do
      ++v23;
    while ( *(_WORD *)(v22 + 2 * v23 + 2) );
    v24 = L" - ";
    if ( v21 )
    {
      v27 = 2 * v21 + 2;
    }
    else
    {
      v25 = -1;
      do
        ++v25;
      while ( *((_WORD *)v2 + v25 + 117) );
      v26 = v25 + 1;
      if ( !v25 )
        v26 = 4;
      v19 = L" - ";
      if ( v25 )
        v19 = (const unsigned __int16 *)((char *)v2 + 234);
      v27 = 2 * v26;
    }
    v12[2].Ptr = (ULONGLONG)v19;
    v12[2].Size = v27;
    v12[2].Reserved = 0;
    if ( v23 )
    {
      v29 = 2 * v23 + 2;
      v24 = (const unsigned __int16 *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v15) + 2610LL);
    }
    else
    {
      do
        ++v20;
      while ( *((_WORD *)v2 + v20 + 16) );
      v28 = v20 + 1;
      if ( v20 )
        v24 = (const unsigned __int16 *)((char *)v2 + 32);
      else
        v28 = 4;
      v29 = 2 * v28;
    }
    v12[1].Ptr = (ULONGLONG)v24;
    v12[1].Size = v29;
    v12[1].Reserved = 0;
    v37 = 0;
    v36 = 0;
    if ( (v13 & 0x800) != 0 )
    {
      v30 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v15);
      v31 = *(_DWORD *)(v30 + 544);
      v36 = v31;
      if ( v31 )
        v16 = (void **)(v30 + 32);
      v32 = VmlpEtwInitializeModuleDescriptors(v16, v31, v11);
      v2 = g_VmlEtwTrace;
      v37 = v32;
      v33 = 4 * v32 + 6;
    }
    else
    {
      v33 = 6;
    }
    *(_QWORD *)&v12[3].Size = 4;
    v12[3].Ptr = (ULONGLONG)&v36;
    v34 = g_TraceLevel < (unsigned __int16)v9;
    v12[4].Size = 8 * v36;
    v12[5].Ptr = (ULONGLONG)&v37;
    v12[4].Ptr = (ULONGLONG)v16;
    v12[4].Reserved = 0;
    *(_QWORD *)&v12[5].Size = 4;
    if ( v34 || (v13 & 0x2000) != 0 )
    {
      if ( (v13 & 0x2000) != 0 )
      {
LABEL_49:
        EventWrite(*((_QWORD *)v2 + 2), *((PCEVENT_DESCRIPTOR *)v2 + v9 + 4135), v33, v12);
LABEL_50:
        if ( v11 )
          operator delete(v11);
        return;
      }
    }
    else
    {
      EventWrite(*((_QWORD *)v2 + 2), EventDescriptor, v33, v12);
      v2 = g_VmlEtwTrace;
    }
    if ( (v13 & 0x1000) == 0 || !*(_BYTE *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v15) + 2608LL) )
      goto LABEL_50;
    goto LABEL_49;
  }
}

```

## disassembly

```asm
0x180019330  push    rbx
0x180019332  push    rbp
0x180019333  push    rsi
0x180019334  push    rdi
0x180019335  push    r12
0x180019337  push    r13
0x180019339  push    r14
0x18001933b  push    r15
0x18001933d  sub     rsp, 0A8h
0x180019344  mov     rax, cs:__security_cookie
0x18001934b  xor     rax, rsp
0x18001934e  mov     [rsp+0E8h+var_58], rax
0x180019356  mov     rsi, cs:?g_VmlEtwTrace@@3PEAU_VML_ETW_TRACE@@EA; _VML_ETW_TRACE * g_VmlEtwTrace
0x18001935d  xor     r9d, r9d
0x180019360  movzx   r14d, cx
0x180019364  mov     r15, rdx
0x180019367  test    rsi, rsi
0x18001936a  jz      loc_18001967B
0x180019370  test    rdx, rdx
0x180019373  jz      short loc_1800193B7
0x180019375  mov     r8d, 400h
0x18001937b  mov     rax, r15
0x18001937e  mov     edx, r8d
0x180019381  cmp     [rax], r9w
0x180019385  jz      short loc_180019391
0x180019387  add     rax, 2
0x18001938b  sub     rdx, 1
0x18001938f  jnz     short loc_180019381
0x180019391  mov     rax, rdx
0x180019394  neg     rax
0x180019397  sbb     ecx, ecx
0x180019399  not     ecx
0x18001939b  and     ecx, 80070057h
0x1800193a1  test    rdx, rdx
0x1800193a4  jz      short loc_1800193BC
0x1800193a6  sub     r8, rdx
0x1800193a9  add     r8, r8
0x1800193ac  neg     rdx
0x1800193af  sbb     rbp, rbp
0x1800193b2  and     rbp, r8
0x1800193b5  jmp     short loc_1800193BF
0x1800193b7  mov     ecx, 80070057h
0x1800193bc  mov     rbp, r9
0x1800193bf  test    ecx, ecx
0x1800193c1  js      loc_18001967B
0x1800193c7  movzx   eax, r14w
0x1800193cb  shr     ax, 0Eh
0x1800193cf  movzx   r13d, ax
0x1800193d3  mov     eax, r14d
0x1800193d6  and     eax, 1Fh
0x1800193d9  lea     ecx, ds:0[rax*4]
0x1800193e0  mov     rax, r14
0x1800193e3  shr     rax, 5
0x1800193e7  add     ecx, r13d
0x1800193ea  and     eax, 1Fh
0x1800193ed  shl     rax, 7
0x1800193f1  add     rcx, rax
0x1800193f4  bt      r14w, 0Bh
0x1800193fa  mov     rax, [rsi+rcx*8+138h]
0x180019402  mov     [rsp+0E8h+EventDescriptor], rax
0x180019407  jnb     short loc_180019431
0x180019409  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180019410  mov     ecx, 8D0h; unsigned __int64
0x180019415  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001941a  mov     rsi, cs:?g_VmlEtwTrace@@3PEAU_VML_ETW_TRACE@@EA; _VML_ETW_TRACE * g_VmlEtwTrace
0x180019421  xor     r9d, r9d
0x180019424  mov     rbx, rax
0x180019427  test    rax, rax
0x18001942a  jz      short loc_180019434
0x18001942c  mov     rdi, rax
0x18001942f  jmp     short loc_18001943C
0x180019431  mov     rbx, r9
0x180019434  mov     rax, r9
0x180019437  lea     rdi, [rsp+0E8h+var_B8]
0x18001943c  mov     ecx, 0F7FFh
0x180019441  movzx   r12d, r14w
0x180019445  and     r12w, cx
0x180019449  lea     rcx, [rdi+10h]; void *
0x18001944d  test    rax, rax
0x180019450  cmovnz  r12w, r14w
0x180019455  xor     edx, edx; Val
0x180019457  lea     r8d, [rdx+50h]; Size
0x18001945b  call    memset_0
0x180019460  lea     eax, [rbp+2]
0x180019463  mov     [rdi], r15
0x180019466  mov     r15d, cs:_tls_index
0x18001946d  xor     ebp, ebp
0x18001946f  mov     [rdi+8], eax
0x180019472  mov     rax, gs:58h
0x18001947b  mov     r11d, 0A30h
0x180019481  mov     [rdi+0Ch], ebp
0x180019484  mov     rdx, [rax+r15*8]
0x180019488  lea     r9, [r11+0CCh]
0x18001948f  add     r9, rdx
0x180019492  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019496  mov     rcx, rax
0x180019499  inc     rcx
0x18001949c  cmp     [r9+rcx*2], bp
0x1800194a1  jnz     short loc_180019499
0x1800194a3  lea     r8, [rdx+r11]
0x1800194a7  mov     rdx, rax
0x1800194aa  inc     rdx
0x1800194ad  cmp     [r8+rdx*2+2], bp
0x1800194b3  jnz     short loc_1800194AA
0x1800194b5  lea     r8, ?NO_VMINFO@_VML_ETW_TRACE@@2QBGB; " - "
0x1800194bc  mov     r14d, 4
0x1800194c2  test    rcx, rcx
0x1800194c5  jnz     short loc_1800194FC
0x1800194c7  lea     r11, [rsi+0EAh]
0x1800194ce  mov     rcx, rax
0x1800194d1  inc     rcx
0x1800194d4  cmp     [r11+rcx*2], bp
0x1800194d9  jnz     short loc_1800194D1
0x1800194db  lea     r10d, [rcx+1]
0x1800194df  test    rcx, rcx
0x1800194e2  jnz     short loc_1800194E7
0x1800194e4  mov     r10d, r14d
0x1800194e7  test    rcx, rcx
0x1800194ea  mov     r9, r8
0x1800194ed  cmovnz  r9, r11
0x1800194f1  add     r10d, r10d
0x1800194f4  mov     r11d, 0A30h
0x1800194fa  jmp     short loc_180019504
0x1800194fc  lea     r10d, ds:2[rcx*2]
0x180019504  mov     [rdi+20h], r9
0x180019508  mov     [rdi+28h], r10d
0x18001950c  mov     [rdi+2Ch], ebp
0x18001950f  test    rdx, rdx
0x180019512  jnz     short loc_180019535
0x180019514  lea     rdx, [rsi+20h]
0x180019518  inc     rax
0x18001951b  cmp     [rdx+rax*2], bp
0x18001951f  jnz     short loc_180019518
0x180019521  lea     ecx, [rax+1]
0x180019524  test    rax, rax
0x180019527  jnz     short loc_18001952C
0x180019529  mov     ecx, r14d
0x18001952c  cmovnz  r8, rdx
0x180019530  lea     edx, [rcx+rcx]
0x180019533  jmp     short loc_180019550
0x180019535  mov     rax, gs:58h
0x18001953e  lea     edx, ds:2[rdx*2]
0x180019545  mov     r8, [rax+r15*8]
0x180019549  add     r8, 2
0x18001954d  add     r8, r11
0x180019550  bt      r12w, 0Bh
0x180019556  mov     [rdi+10h], r8
0x18001955a  mov     [rdi+18h], edx
0x18001955d  mov     [rdi+1Ch], ebp
0x180019560  mov     [rsp+0E8h+var_BC], ebp
0x180019564  mov     [rsp+0E8h+var_C0], ebp
0x180019568  jnb     short loc_1800195B0
0x18001956a  mov     rax, gs:58h
0x180019573  mov     edx, 220h
0x180019578  mov     r8, [rax+r15*8]
0x18001957c  mov     edx, [rdx+r8]; unsigned int
0x180019580  mov     [rsp+0E8h+var_C0], edx
0x180019584  test    edx, edx
0x180019586  jz      short loc_180019590
0x180019588  mov     ebp, 20h ; ' '
0x18001958d  add     rbp, r8
0x180019590  mov     r8, rbx; struct VmlEventDataForStackTrace *
0x180019593  mov     rcx, rbp; void **
0x180019596  call    ?VmlpEtwInitializeModuleDescriptors@@YAKPEAPEAXKPEAUVmlEventDataForStackTrace@@@Z; VmlpEtwInitializeModuleDescriptors(void * *,ulong,VmlEventDataForStackTrace *)
0x18001959b  mov     rsi, cs:?g_VmlEtwTrace@@3PEAU_VML_ETW_TRACE@@EA; _VML_ETW_TRACE * g_VmlEtwTrace
0x1800195a2  mov     [rsp+0E8h+var_BC], eax
0x1800195a6  lea     r14d, ds:6[rax*4]
0x1800195ae  jmp     short loc_1800195B6
0x1800195b0  mov     r14d, 6
0x1800195b6  lea     rax, [rsp+0E8h+var_C0]
0x1800195bb  mov     qword ptr [rdi+38h], 4
0x1800195c3  mov     [rdi+30h], rax
0x1800195c7  mov     eax, [rsp+0E8h+var_C0]
0x1800195cb  shl     eax, 3
0x1800195ce  cmp     cs:?g_TraceLevel@@3GA, r13w; ushort g_TraceLevel
0x1800195d6  mov     [rdi+48h], eax
0x1800195d9  lea     rax, [rsp+0E8h+var_BC]
0x1800195de  mov     [rdi+50h], rax
0x1800195e2  mov     [rdi+40h], rbp
0x1800195e6  mov     dword ptr [rdi+4Ch], 0
0x1800195ed  mov     qword ptr [rdi+58h], 4
0x1800195f5  jb      short loc_180019623
0x1800195f7  bt      r12w, 0Dh
0x1800195fd  jb      short loc_180019623
0x1800195ff  mov     rdx, [rsp+0E8h+EventDescriptor]; EventDescriptor
0x180019604  mov     r9, rdi; UserData
0x180019607  mov     rcx, [rsi+10h]; RegHandle
0x18001960b  mov     r8d, r14d; UserDataCount
0x18001960e  call    cs:__imp_EventWrite
0x180019615  nop     dword ptr [rax+rax+00h]
0x18001961a  mov     rsi, cs:?g_VmlEtwTrace@@3PEAU_VML_ETW_TRACE@@EA; _VML_ETW_TRACE * g_VmlEtwTrace
0x180019621  jmp     short loc_18001962B
0x180019623  bt      r12w, 0Dh
0x180019629  jb      short loc_18001964B
0x18001962b  bt      r12w, 0Ch
0x180019631  jnb     short loc_180019669
0x180019633  mov     rax, gs:58h
0x18001963c  mov     rcx, [rax+r15*8]
0x180019640  mov     eax, 0A30h
0x180019645  cmp     byte ptr [rax+rcx], 0
0x180019649  jz      short loc_180019669
0x18001964b  mov     rdx, [rsi+r13*8+8138h]; EventDescriptor
0x180019653  mov     r9, rdi; UserData
0x180019656  mov     rcx, [rsi+10h]; RegHandle
0x18001965a  mov     r8d, r14d; UserDataCount
0x18001965d  call    cs:__imp_EventWrite
0x180019664  nop     dword ptr [rax+rax+00h]
0x180019669  test    rbx, rbx
0x18001966c  jz      short loc_18001967B
0x18001966e  mov     edx, 8D0h; unsigned __int64
0x180019673  mov     rcx, rbx; void *
0x180019676  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001967b  mov     rcx, [rsp+0E8h+var_58]
0x180019683  xor     rcx, rsp; StackCookie
0x180019686  call    __security_check_cookie
0x18001968b  add     rsp, 0A8h
0x180019692  pop     r15
0x180019694  pop     r14
0x180019696  pop     r13
0x180019698  pop     r12
0x18001969a  pop     rdi
0x18001969b  pop     rsi
0x18001969c  pop     rbp
0x18001969d  pop     rbx
0x18001969e  retn
```
