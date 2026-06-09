# CBaseUI::AddPages(CPage * *,ulong)

- ea: `0x1800131f0`
- end: `0x180013408`
- name: `?AddPages@CBaseUI@@MEAAKPEAPEAVCPage@@K@Z`
- size: `536`
- prototype: `unsigned int __fastcall(CBaseUI *__hidden this, struct CPage **, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800101a0`

## callees

- `0x180005eac`
- `0x18000f898`
- `0x18000fac4`
- `0x1800131f0`
- `0x18001394c`
- `0x180015cbe`
- `0x180017010`

## import_xrefs

- `KERNEL32!DeactivateActCtx` at `0x18001333a`
- `KERNEL32!DeactivateActCtx` at `0x18001333a`

## string_xrefs

- `0x1800132e6`: `CreatePropertySheetPageW`

## pseudocode

```c
unsigned int __fastcall CBaseUI::AddPages(CBaseUI *this, struct CPage **a2, unsigned int a3)
{
  _QWORD *v6; // rcx
  unsigned int result; // eax
  unsigned int v8; // edi
  __int64 v9; // rbp
  __int64 v10; // r14
  __int64 (__fastcall *v11)(unsigned int *); // rax
  __int64 v12; // rcx
  int v13; // ecx
  unsigned int v14; // [rsp+20h] [rbp-A8h] BYREF
  int v15; // [rsp+24h] [rbp-A4h]
  HANDLE v16; // [rsp+78h] [rbp-50h]
  ULONG_PTR ulCookie; // [rsp+D8h] [rbp+10h] BYREF

  memset_0(&v14, 0, 0x68u);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_fa70d120337031dac9c0bc835e4c3cf9_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( a2 && a3 )
  {
    result = CBaseUI::InitializePageArray(this, a3);
    v8 = result;
    if ( result )
      return result;
    if ( *((_DWORD *)this + 35) + a3 <= *((_DWORD *)this + 34) )
    {
      v9 = 0;
      while ( 1 )
      {
        (*(void (__fastcall **)(struct CPage *, unsigned int *))(*(_QWORD *)a2[v9] + 40LL))(a2[v9], &v14);
        ulCookie = 0;
        v10 = 0;
        SHActivateContext(&ulCookie);
        v11 = (__int64 (__fastcall *)(unsigned int *))qword_18001E4F8;
        if ( qword_18001E4F8 == -1 )
        {
          GetProcFromComCtl32(&qword_18001E4F8, "CreatePropertySheetPageW");
          v11 = (__int64 (__fastcall *)(unsigned int *))qword_18001E4F8;
        }
        if ( v11 )
        {
          if ( v14 > 0x58 )
          {
            v15 |= 0x4000u;
            v16 = g_hActCtx;
          }
          v10 = v11(&v14);
        }
        if ( ulCookie )
          DeactivateActCtx(0, ulCookie);
        *(_QWORD *)(*((_QWORD *)this + 4) + 8LL * *((unsigned int *)this + 35)) = v10;
        v12 = *((unsigned int *)this + 35);
        if ( !*(_QWORD *)(*((_QWORD *)this + 4) + 8 * v12) )
          break;
        v13 = v12 + 1;
        v9 = (unsigned int)(v9 + 1);
        *((_DWORD *)this + 35) = v13;
        if ( (unsigned int)v9 >= a3 )
        {
          if ( v13 == *((_DWORD *)this + 34) )
            (*(void (__fastcall **)(CBaseUI *))(*(_QWORD *)this + 16LL))(this);
          return v8;
        }
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_fa70d120337031dac9c0bc835e4c3cf9_Traceguids);
      }
      return 8;
    }
    else
    {
      return 111;
    }
  }
  else
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x100) != 0 && *((_BYTE *)v6 + 25) >= 2u )
      WPP_SF_(v6[2], 17, WPP_fa70d120337031dac9c0bc835e4c3cf9_Traceguids);
    return 87;
  }
}

```

## disassembly

```asm
0x1800131f0  push    rbx
0x1800131f2  push    rbp
0x1800131f3  push    rsi
0x1800131f4  push    rdi
0x1800131f5  push    r14
0x1800131f7  push    r15
0x1800131f9  sub     rsp, 98h
0x180013200  mov     r15, rdx
0x180013203  mov     esi, r8d
0x180013206  xor     edx, edx; Val
0x180013208  mov     rbx, rcx
0x18001320b  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180013210  lea     r8d, [rdx+68h]; Size
0x180013214  call    memset_0
0x180013219  mov     rcx, cs:WPP_GLOBAL_Control
0x180013220  lea     rax, WPP_GLOBAL_Control
0x180013227  cmp     rcx, rax
0x18001322a  jz      short loc_18001325E
0x18001322c  test    dword ptr [rcx+1Ch], 100h
0x180013233  jz      short loc_18001325E
0x180013235  cmp     byte ptr [rcx+19h], 5
0x180013239  jb      short loc_18001325E
0x18001323b  mov     rcx, [rcx+10h]
0x18001323f  lea     r8, WPP_fa70d120337031dac9c0bc835e4c3cf9_Traceguids
0x180013246  mov     edx, 10h
0x18001324b  call    WPP_SF_
0x180013250  mov     rcx, cs:WPP_GLOBAL_Control
0x180013257  lea     rax, WPP_GLOBAL_Control
0x18001325e  test    r15, r15
0x180013261  jz      loc_1800133C8
0x180013267  test    esi, esi
0x180013269  jz      loc_1800133C8
0x18001326f  mov     edx, esi; unsigned int
0x180013271  mov     rcx, rbx; this
0x180013274  call    ?InitializePageArray@CBaseUI@@AEAAKK@Z; CBaseUI::InitializePageArray(ulong)
0x180013279  mov     edi, eax
0x18001327b  test    eax, eax
0x18001327d  jnz     loc_1800133F8
0x180013283  mov     ecx, [rbx+8Ch]
0x180013289  lea     eax, [rcx+rsi]
0x18001328c  cmp     eax, [rbx+88h]
0x180013292  jbe     short loc_18001329E
0x180013294  mov     edi, 6Fh ; 'o'
0x180013299  jmp     loc_1800133F6
0x18001329e  xor     ebp, ebp
0x1800132a0  test    esi, esi
0x1800132a2  jz      loc_180013371
0x1800132a8  mov     rcx, [r15+rbp*8]
0x1800132ac  lea     rdx, [rsp+0C8h+var_A8]
0x1800132b1  mov     rax, [rcx]
0x1800132b4  mov     rax, [rax+28h]
0x1800132b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132bd  lea     rcx, [rsp+0C8h+ulCookie]
0x1800132c5  mov     [rsp+0C8h+ulCookie], 0
0x1800132d1  xor     r14d, r14d
0x1800132d4  call    SHActivateContext
0x1800132d9  mov     rax, cs:qword_18001E4F8
0x1800132e0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800132e4  jnz     short loc_180013300
0x1800132e6  lea     rdx, aCreateproperty; "CreatePropertySheetPageW"
0x1800132ed  lea     rcx, qword_18001E4F8
0x1800132f4  call    _GetProcFromComCtl32
0x1800132f9  mov     rax, cs:qword_18001E4F8
0x180013300  test    rax, rax
0x180013303  jz      short loc_18001332B
0x180013305  cmp     [rsp+0C8h+var_A8], 58h ; 'X'
0x18001330a  jbe     short loc_18001331E
0x18001330c  mov     rcx, cs:g_hActCtx
0x180013313  bts     [rsp+0C8h+var_A4], 0Eh
0x180013319  mov     [rsp+0C8h+var_50], rcx
0x18001331e  lea     rcx, [rsp+0C8h+var_A8]
0x180013323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013328  mov     r14, rax
0x18001332b  mov     rdx, [rsp+0C8h+ulCookie]; ulCookie
0x180013333  test    rdx, rdx
0x180013336  jz      short loc_180013340
0x180013338  xor     ecx, ecx; dwFlags
0x18001333a  call    cs:__imp_DeactivateActCtx
0x180013340  mov     rcx, [rbx+20h]
0x180013344  mov     edx, [rbx+8Ch]
0x18001334a  mov     [rcx+rdx*8], r14
0x18001334e  mov     ecx, [rbx+8Ch]
0x180013354  mov     rax, [rbx+20h]
0x180013358  cmp     qword ptr [rax+rcx*8], 0
0x18001335d  jz      short loc_18001338A
0x18001335f  inc     ecx
0x180013361  inc     ebp
0x180013363  mov     [rbx+8Ch], ecx
0x180013369  cmp     ebp, esi
0x18001336b  jb      loc_1800132A8
0x180013371  cmp     ecx, [rbx+88h]
0x180013377  jnz     short loc_1800133F6
0x180013379  mov     rax, [rbx]
0x18001337c  mov     rcx, rbx
0x18001337f  mov     rax, [rax+10h]
0x180013383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013388  jmp     short loc_1800133F6
0x18001338a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013391  lea     rax, WPP_GLOBAL_Control
0x180013398  cmp     rcx, rax
0x18001339b  jz      short loc_1800133C1
0x18001339d  test    dword ptr [rcx+1Ch], 100h
0x1800133a4  jz      short loc_1800133C1
0x1800133a6  cmp     byte ptr [rcx+19h], 2
0x1800133aa  jb      short loc_1800133C1
0x1800133ac  mov     rcx, [rcx+10h]
0x1800133b0  lea     r8, WPP_fa70d120337031dac9c0bc835e4c3cf9_Traceguids
0x1800133b7  mov     edx, 12h
0x1800133bc  call    WPP_SF_
0x1800133c1  mov     edi, 8
0x1800133c6  jmp     short loc_1800133F6
0x1800133c8  cmp     rcx, rax
0x1800133cb  jz      short loc_1800133F1
0x1800133cd  test    dword ptr [rcx+1Ch], 100h
0x1800133d4  jz      short loc_1800133F1
0x1800133d6  cmp     byte ptr [rcx+19h], 2
0x1800133da  jb      short loc_1800133F1
0x1800133dc  mov     rcx, [rcx+10h]
0x1800133e0  lea     r8, WPP_fa70d120337031dac9c0bc835e4c3cf9_Traceguids
0x1800133e7  mov     edx, 11h
0x1800133ec  call    WPP_SF_
0x1800133f1  mov     edi, 57h ; 'W'
0x1800133f6  mov     eax, edi
0x1800133f8  add     rsp, 98h
0x1800133ff  pop     r15
0x180013401  pop     r14
0x180013403  pop     rdi
0x180013404  pop     rsi
0x180013405  pop     rbp
0x180013406  pop     rbx
0x180013407  retn
```
