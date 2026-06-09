# SslExpandWriteKey

- ea: `0x180012580`
- end: `0x180012a5e`
- name: `SslExpandWriteKey`
- size: `1246`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a770`
- `0x18000d02c`
- `0x18000e120`
- `0x180012580`
- `0x180020010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18001261b`
- `ntdll!RtlAllocateHeap` at `0x18001261b`

## string_xrefs

- `0x1800126c0`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180012879`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x1800128d2`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x1800128ed`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180012912`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
__int64 __fastcall SslExpandWriteKey(_DWORD *a1, _DWORD *a2, _QWORD *a3, __int64 a4, int a5)
{
  _DWORD *v7; // rbp
  _DWORD *v8; // rbx
  unsigned int v9; // esi
  _OWORD *Heap; // rax
  _OWORD *v11; // rdi
  int v12; // edx
  unsigned int v13; // ebp
  int v14; // r8d
  __int64 v16; // r9
  __int64 v17; // rcx

  v7 = a2;
  v8 = a1;
  if ( !a1 || *a1 < 0x1B0u || a1[1] != 1145324609 || a1[3] )
    v8 = 0;
  if ( !a2 || *a2 < 0x20u || a2[1] != 1145324610 )
    v7 = 0;
  v9 = -2146893786;
  if ( v8 && v7 )
  {
    if ( a3 )
    {
      if ( *((_WORD *)v8 + 16) < 4u )
      {
        v13 = -2146893783;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (_DWORD)a2,
            (_DWORD)a3,
            (unsigned int)"Status",
            41,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
            13);
          return v13;
        }
        goto LABEL_22;
      }
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x20u);
      v11 = Heap;
      if ( Heap )
      {
        *Heap = 0;
        Heap[1] = 0;
        v13 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _OWORD *, __int64, int))v8 + 39))(
                *((_QWORD *)v8 + 53),
                *((_QWORD *)v7 + 2),
                Heap + 1,
                a4,
                a5);
        if ( (v13 & 0x80000000) == 0 )
        {
          *(_DWORD *)v11 = 32;
          *(_QWORD *)((char *)v11 + 4) = 1145324610;
          *((_DWORD *)v11 + 3) = 1;
          *((_QWORD *)v11 + 3) = v8;
          *a3 = v11;
          _InterlockedIncrement(v8 + 4);
          return 0;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v12,
            v14,
            (unsigned int)"Status",
            v13,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
            42);
        MSCryptFree(v11);
        goto LABEL_22;
      }
      v13 = -2146893810;
      v16 = 4121;
      v17 = 2148073486LL;
    }
    else
    {
      v13 = -2146893785;
      v16 = 4098;
      v17 = 2148073511LL;
    }
    DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", v16);
    return v13;
  }
  v13 = -2146893786;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)a2,
      (_DWORD)a3,
      (unsigned int)"Status",
      38,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
      251);
    return v13;
  }
LABEL_22:
  if ( (v13 & 0x1FFF0000) != 0x90000 && (v13 & 0x1FFF0000) != 0x100000 )
  {
    if ( v13 > 0xC000007B )
    {
      if ( v13 <= 0xC0000135 )
      {
        if ( v13 == -1073741515 )
          return (unsigned int)-2146893794;
        if ( v13 == -1073741637 )
          return (unsigned int)-2146893783;
        if ( v13 != -1073741670 )
        {
          if ( v13 == -1073741595 )
            return (unsigned int)-2146893779;
          return v13;
        }
        return (unsigned int)-2146893810;
      }
      if ( v13 != -1073741502 )
      {
        if ( v13 == -1073700864 )
          return (unsigned int)-2146893818;
        if ( v13 != -1073741511 )
          return v13;
      }
    }
    else if ( v13 != -1073741701 )
    {
      if ( v13 == -1073741816 )
        return v9;
      if ( v13 <= 0xC0000008 )
      {
        switch ( v13 )
        {
          case 0x800704C0:
            return (unsigned int)-2147023680;
          case 0x800704C7:
            return (unsigned int)-2147023673;
          case 0x80070578:
            return (unsigned int)-2147023496;
        }
        return v13;
      }
      if ( v13 == -1073741811 )
        return (unsigned int)-2146893785;
      if ( v13 != -1073741801 )
      {
        if ( v13 == -1073741789 )
          return (unsigned int)-2146893784;
        return v13;
      }
      return (unsigned int)-2146893810;
    }
    return (unsigned int)-2146893795;
  }
  return v13;
}

```

## disassembly

```asm
0x180012580  mov     [rsp+arg_8], rbx
0x180012585  mov     [rsp+arg_10], rbp
0x18001258a  push    rsi
0x18001258b  push    r14
0x18001258d  push    r15
0x18001258f  sub     rsp, 40h
0x180012593  mov     r15, r9
0x180012596  mov     r14, r8
0x180012599  mov     rbp, rdx
0x18001259c  mov     rbx, rcx
0x18001259f  test    rcx, rcx
0x1800125a2  jz      short loc_1800125BB
0x1800125a4  cmp     dword ptr [rcx], 1B0h
0x1800125aa  jb      short loc_1800125BB
0x1800125ac  cmp     dword ptr [rcx+4], 44444441h
0x1800125b3  jnz     short loc_1800125BB
0x1800125b5  cmp     dword ptr [rcx+0Ch], 0
0x1800125b9  jz      short loc_1800125BD
0x1800125bb  xor     ebx, ebx
0x1800125bd  test    rdx, rdx
0x1800125c0  jz      short loc_1800125D0
0x1800125c2  cmp     dword ptr [rdx], 20h ; ' '
0x1800125c5  jb      short loc_1800125D0
0x1800125c7  cmp     dword ptr [rdx+4], 44444442h
0x1800125ce  jz      short loc_1800125D2
0x1800125d0  xor     ebp, ebp
0x1800125d2  mov     [rsp+58h+arg_0], rdi
0x1800125d7  mov     esi, 80090026h
0x1800125dc  test    rbx, rbx
0x1800125df  jz      loc_18001284E
0x1800125e5  test    rbp, rbp
0x1800125e8  jz      loc_18001284E
0x1800125ee  test    r14, r14
0x1800125f1  jz      loc_1800128E8
0x1800125f7  mov     eax, 4
0x1800125fc  cmp     ax, [rbx+20h]
0x180012600  ja      loc_1800128A4
0x180012606  mov     rcx, gs:60h
0x18001260f  xor     edx, edx; Flags
0x180012611  mov     r8d, 20h ; ' '; Size
0x180012617  mov     rcx, [rcx+30h]; HeapHandle
0x18001261b  call    cs:__imp_RtlAllocateHeap
0x180012621  mov     rdi, rax
0x180012624  test    rax, rax
0x180012627  jz      loc_18001290D
0x18001262d  mov     ecx, [rsp+58h+arg_20]
0x180012634  lea     r8, [rax+10h]
0x180012638  xorps   xmm0, xmm0
0x18001263b  mov     [rsp+58h+var_38], ecx
0x18001263f  movups  xmmword ptr [rax], xmm0
0x180012642  mov     r9, r15
0x180012645  movups  xmmword ptr [rax+10h], xmm0
0x180012649  mov     rdx, [rbp+10h]
0x18001264d  mov     rcx, [rbx+1A8h]
0x180012654  mov     rax, [rbx+138h]
0x18001265b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012660  mov     ebp, eax
0x180012662  test    eax, eax
0x180012664  js      short loc_1800126A3
0x180012666  mov     dword ptr [rdi], 20h ; ' '
0x18001266c  mov     qword ptr [rdi+4], 44444442h
0x180012674  mov     dword ptr [rdi+0Ch], 1
0x18001267b  mov     [rdi+18h], rbx
0x18001267f  mov     [r14], rdi
0x180012682  lock inc dword ptr [rbx+10h]
0x180012686  xor     esi, esi
0x180012688  mov     eax, esi
0x18001268a  mov     rdi, [rsp+58h+arg_0]
0x18001268f  mov     rbx, [rsp+58h+arg_8]
0x180012694  mov     rbp, [rsp+58h+arg_10]
0x180012699  add     rsp, 40h
0x18001269d  pop     r15
0x18001269f  pop     r14
0x1800126a1  pop     rsi
0x1800126a2  retn
0x1800126a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800126aa  lea     rax, WPP_GLOBAL_Control
0x1800126b1  cmp     rcx, rax
0x1800126b4  jz      short loc_1800126E4
0x1800126b6  test    byte ptr [rcx+1Ch], 1
0x1800126ba  jz      short loc_1800126E4
0x1800126bc  mov     rcx, [rcx+10h]
0x1800126c0  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800126c7  mov     [rsp+58h+var_28], 102Ah
0x1800126cf  lea     r9, aStatus; "Status"
0x1800126d6  mov     [rsp+58h+var_30], rax
0x1800126db  mov     [rsp+58h+var_38], ebp
0x1800126df  call    WPP_SF_sDsd
0x1800126e4  mov     rcx, rdi
0x1800126e7  call    MSCryptFree
0x1800126ec  mov     eax, ebp
0x1800126ee  and     eax, 1FFF0000h
0x1800126f3  cmp     eax, 90000h
0x1800126f8  jz      loc_18001289D
0x1800126fe  cmp     eax, 100000h
0x180012703  jz      loc_18001289D
0x180012709  test    ebp, ebp
0x18001270b  jz      loc_180012686
0x180012711  cmp     ebp, 216h
0x180012717  ja      short loc_180012752
0x180012719  jz      loc_18001281C
0x18001271f  lea     eax, [rbp-2]; switch 182 cases
0x180012722  cmp     eax, 0B5h
0x180012727  ja      def_180012746; jumptable 0000000180012746 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18001272d  lea     rdx, __ImageBase
0x180012734  movzx   eax, ds:(byte_1800129A8 - 180000000h)[rdx+rax]
0x18001273c  mov     ecx, ds:(jpt_180012746 - 180000000h)[rdx+rax*4]
0x180012743  add     rcx, rdx
0x180012746  jmp     rcx; switch jump
0x180012748  mov     esi, 80090027h; jumptable 0000000180012746 case 87
0x18001274d  jmp     loc_180012688
0x180012752  cmp     ebp, 0C000007Bh
0x180012758  ja      short loc_1800127A8
0x18001275a  jz      loc_180012844
0x180012760  cmp     ebp, 0C0000008h
0x180012766  jz      loc_180012688
0x18001276c  ja      loc_18001292D
0x180012772  cmp     ebp, 800704C0h
0x180012778  jz      short loc_1800127EA
0x18001277a  cmp     ebp, 54Fh
0x180012780  jz      loc_18001296B
0x180012786  cmp     ebp, 800704C7h
0x18001278c  jz      loc_180012826
0x180012792  cmp     ebp, 80070578h
0x180012798  jnz     def_180012746; jumptable 0000000180012746 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18001279e  mov     esi, 80070578h
0x1800127a3  jmp     loc_180012688
0x1800127a8  cmp     ebp, 0C0000135h
0x1800127ae  ja      short loc_1800127CC
0x1800127b0  jz      loc_18001283A
0x1800127b6  cmp     ebp, 0C00000BBh
0x1800127bc  jnz     loc_180012957
0x1800127c2  mov     esi, 80090029h
0x1800127c7  jmp     loc_180012688
0x1800127cc  cmp     ebp, 0C0000142h
0x1800127d2  jz      short loc_180012844
0x1800127d4  cmp     ebp, 0C000A000h
0x1800127da  jnz     loc_180012975
0x1800127e0  mov     esi, 80090006h
0x1800127e5  jmp     loc_180012688
0x1800127ea  mov     esi, 800704C0h
0x1800127ef  jmp     loc_180012688
0x1800127f4  mov     esi, 80090011h; jumptable 0000000180012746 cases 2,3
0x1800127f9  jmp     loc_180012688
0x1800127fe  mov     esi, 80090010h; jumptable 0000000180012746 case 5
0x180012803  jmp     loc_180012688
0x180012808  mov     esi, 80070070h; jumptable 0000000180012746 case 112
0x18001280d  jmp     loc_180012688
0x180012812  mov     esi, 8009000Fh; jumptable 0000000180012746 case 183
0x180012817  jmp     loc_180012688
0x18001281c  mov     esi, 80070216h
0x180012821  jmp     loc_180012688
0x180012826  mov     esi, 800704C7h
0x18001282b  jmp     loc_180012688
0x180012830  mov     esi, 8009000Eh; jumptable 0000000180012746 cases 8,14
0x180012835  jmp     loc_180012688
0x18001283a  mov     esi, 8009001Eh
0x18001283f  jmp     loc_180012688
0x180012844  mov     esi, 8009001Dh
0x180012849  jmp     loc_180012688
0x18001284e  mov     ebp, esi
0x180012850  mov     rcx, cs:WPP_GLOBAL_Control
0x180012857  lea     rax, WPP_GLOBAL_Control
0x18001285e  cmp     rcx, rax
0x180012861  jz      loc_1800126EC
0x180012867  test    byte ptr [rcx+1Ch], 1
0x18001286b  jz      loc_1800126EC
0x180012871  mov     [rsp+58h+var_28], 0FFBh
0x180012879  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012880  mov     [rsp+58h+var_30], rax
0x180012885  mov     [rsp+58h+var_38], 80090026h
0x18001288d  mov     rcx, [rcx+10h]
0x180012891  lea     r9, aStatus; "Status"
0x180012898  call    WPP_SF_sDsd
0x18001289d  mov     eax, ebp
0x18001289f  jmp     loc_18001268A
0x1800128a4  mov     ebp, 80090029h
0x1800128a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800128b0  lea     rax, WPP_GLOBAL_Control
0x1800128b7  cmp     rcx, rax
0x1800128ba  jz      loc_1800126EC
0x1800128c0  test    byte ptr [rcx+1Ch], 1
0x1800128c4  jz      loc_1800126EC
0x1800128ca  mov     [rsp+58h+var_28], 100Dh
0x1800128d2  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800128d9  mov     [rsp+58h+var_30], rax
0x1800128de  mov     [rsp+58h+var_38], 80090029h
0x1800128e6  jmp     short loc_18001288D
0x1800128e8  mov     ebp, 80090027h
0x1800128ed  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800128f4  mov     r9d, 1002h
0x1800128fa  lea     rdx, aStatus; "Status"
0x180012901  mov     ecx, 80090027h
0x180012906  call    DebugTraceError
0x18001290b  jmp     short loc_18001289D
0x18001290d  mov     ebp, 8009000Eh
0x180012912  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012919  mov     r9d, 1019h
0x18001291f  lea     rdx, aStatus; "Status"
0x180012926  mov     ecx, 8009000Eh
0x18001292b  jmp     short loc_180012906
0x18001292d  cmp     ebp, 0C000000Dh
0x180012933  jz      loc_180012748; jumptable 0000000180012746 case 87
0x180012939  cmp     ebp, 0C0000017h
0x18001293f  jz      loc_180012830; jumptable 0000000180012746 cases 8,14
0x180012945  cmp     ebp, 0C0000023h
0x18001294b  jnz     short def_180012746; jumptable 0000000180012746 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18001294d  mov     esi, 80090028h; jumptable 0000000180012746 case 122
0x180012952  jmp     loc_180012688
0x180012957  cmp     ebp, 0C000009Ah
0x18001295d  jz      loc_180012830; jumptable 0000000180012746 cases 8,14
0x180012963  cmp     ebp, 0C00000E5h
0x180012969  jnz     short def_180012746; jumptable 0000000180012746 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18001296b  mov     esi, 8009002Dh
0x180012970  jmp     loc_180012688
0x180012975  cmp     ebp, 0C0000139h
0x18001297b  jz      loc_180012844
0x180012981  mov     esi, ebp; jumptable 0000000180012746 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x180012983  jmp     loc_180012688
```
