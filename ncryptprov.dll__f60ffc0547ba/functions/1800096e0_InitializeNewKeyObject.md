# InitializeNewKeyObject

- ea: `0x1800096e0`
- end: `0x180009b4d`
- name: `InitializeNewKeyObject`
- size: `1133`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, void *@<rdx>, int, int, int, int, int, void *, __int64)`
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009f60`
- `0x18002b460`
- `0x18002c7b0`

## callees

- `0x1800096e0`
- `0x18000af80`
- `0x18000b250`
- `0x18000d3d0`
- `0x18000def0`
- `0x180038970`
- `0x1800398b0`
- `0x18004de14`
- `0x18004df10`

## import_xrefs

- `ntdll!RtlInitializeResource` at `0x180009902`
- `ntdll!RtlInitializeResource` at `0x180009902`
- `ntdll!RtlAllocateHeap` at `0x18000970f`
- `ntdll!RtlAllocateHeap` at `0x180009874`
- `ntdll!RtlAllocateHeap` at `0x1800099ba`
- `ntdll!RtlAllocateHeap` at `0x18000970f`
- `ntdll!RtlAllocateHeap` at `0x180009874`
- `ntdll!RtlAllocateHeap` at `0x1800099ba`

## string_xrefs

- `0x18000991b`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18000995b`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x180009a14`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x180009ae8`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`

## pseudocode

```c
__int64 __fastcall InitializeNewKeyObject(
        _WORD *Src,
        _WORD *a2,
        __int64 a3,
        int a4,
        __int16 a5,
        int a6,
        int a7,
        int a8,
        int a9,
        _WORD *Srca,
        _QWORD *a11)
{
  char *Heap; // rax
  int v16; // edx
  int v17; // r8d
  char *v18; // rsi
  int v19; // edx
  int v20; // r8d
  __int64 v21; // rbx
  size_t v22; // rbx
  PVOID v23; // rax
  unsigned int v24; // ebx
  _QWORD *v25; // rcx
  __int64 v27; // rax
  unsigned int v28; // eax
  unsigned int v29; // r15d
  PVOID v30; // rax
  __int64 v31; // rax
  unsigned int v32; // r15d
  void *v33; // rax
  __int64 v34; // r9
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  char v39; // [rsp+30h] [rbp-58h]

  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x248u);
  v18 = Heap;
  if ( Heap )
  {
    memset_0(Heap, 0, 0x248u);
    *(_DWORD *)v18 = 584;
    *((_DWORD *)v18 + 1) = 1263751243;
    *((_DWORD *)v18 + 6) = a4;
    *((_DWORD *)v18 + 10) = 0xFFFFFF;
    *((_DWORD *)v18 + 131) = a9;
    *((_DWORD *)v18 + 132) = a6;
    *((_DWORD *)v18 + 133) = a7;
    *((_DWORD *)v18 + 134) = a8;
    *((_QWORD *)v18 + 12) = 0;
    *((_DWORD *)v18 + 135) = a6 == 0;
    if ( a3 )
    {
      *((_QWORD *)v18 + 8) = a3;
      *((_DWORD *)v18 + 7) = *(_DWORD *)(a3 + 60);
    }
    *((_OWORD *)v18 + 27) = 0;
    *((_OWORD *)v18 + 28) = 0;
    *((_OWORD *)v18 + 29) = 0;
    *((_OWORD *)v18 + 30) = 0;
    if ( !dword_18007A698 )
    {
      g_dwStrongKeyCacheDuration = KspInitStrongKeyCacheDuration();
      dword_18007A698 = 1;
    }
    if ( g_dwStrongKeyForcePassword == -1 )
      g_dwStrongKeyForcePassword = KspInitStrongKeyForcePassword();
    *((_QWORD *)v18 + 62) = 0;
    *((_DWORD *)v18 + 106) = 0;
    *((_QWORD *)v18 + 52) = 0;
    if ( (a5 & 0x20) != 0 )
      *((_DWORD *)v18 + 8) = 1;
    if ( (a5 & 0x4000) != 0 )
      *((_DWORD *)v18 + 107) |= 0x40u;
    v21 = -1;
    if ( !Src )
    {
      *((_DWORD *)v18 + 142) = 1;
      goto LABEL_14;
    }
    v27 = -1;
    do
      ++v27;
    while ( Src[v27] );
    v28 = v27 + 1;
    if ( v28 <= 0x104 )
    {
      v29 = 2 * v28;
      v30 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2 * v28);
      *((_QWORD *)v18 + 1) = v30;
      if ( !v30 )
      {
        v34 = 1077;
        goto LABEL_43;
      }
      memcpy_0(v30, Src, v29);
LABEL_14:
      if ( !Srca )
        goto LABEL_15;
      v31 = -1;
      do
        ++v31;
      while ( Srca[v31] );
      v32 = 2 * v31 + 2;
      v33 = (void *)SafeAllocaAllocateFromHeap(v32);
      *((_QWORD *)v18 + 10) = v33;
      if ( v33 )
      {
        memcpy_0(v33, Srca, v32);
LABEL_15:
        if ( a2 )
        {
          do
            ++v21;
          while ( a2[v21] );
          v22 = (unsigned int)(2 * v21 + 2);
          v23 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)v22);
          *((_QWORD *)v18 + 7) = v23;
          if ( !v23 )
          {
            v24 = -2146893810;
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_20;
            v39 = 94;
LABEL_25:
            WPP_SF_sDsd(
              v25[2],
              v16,
              v17,
              (unsigned int)"Status",
              14,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
              v39);
            goto LABEL_20;
          }
          memcpy_0(v23, a2, v22);
        }
        *((_QWORD *)v18 + 37) = v18 + 288;
        *((_QWORD *)v18 + 36) = v18 + 288;
        *((_QWORD *)v18 + 21) = &NormalModeBCryptSecretsFuncTable;
        RtlInitializeResource((PRTL_RESOURCE)(v18 + 304));
        *a11 = v18;
        v18 = 0;
        v24 = 0;
        goto LABEL_20;
      }
      v34 = 1103;
LABEL_43:
      v24 = -2146893810;
      DebugTraceError(2148073486LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c", v34);
      goto LABEL_20;
    }
    v24 = -2146893785;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v19,
        v20,
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
        42);
  }
  else
  {
    v24 = -2146893810;
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v39 = -37;
      goto LABEL_25;
    }
  }
LABEL_20:
  if ( v18 )
  {
    v35 = *((_QWORD *)v18 + 52);
    if ( v35 )
      MSCryptFree(v35);
    v36 = *((_QWORD *)v18 + 1);
    if ( v36 )
      MSCryptFree(v36);
    v37 = *((_QWORD *)v18 + 7);
    if ( v37 )
      MSCryptFree(v37);
    v38 = *((_QWORD *)v18 + 10);
    if ( v38 )
      MSCryptFree(v38);
    MSCryptFree(v18);
  }
  return v24;
}

```

## disassembly

```asm
0x1800096e0  push    rbx
0x1800096e2  push    rsi
0x1800096e3  push    rdi
0x1800096e4  push    r12
0x1800096e6  push    r14
0x1800096e8  push    r15
0x1800096ea  sub     rsp, 58h
0x1800096ee  mov     r15d, r9d
0x1800096f1  mov     rbx, r8
0x1800096f4  mov     rdi, rdx
0x1800096f7  mov     r14, rcx
0x1800096fa  mov     rcx, gs:60h
0x180009703  xor     edx, edx; Flags
0x180009705  mov     r8d, 248h; Size
0x18000970b  mov     rcx, [rcx+30h]; HeapHandle
0x18000970f  call    cs:__imp_RtlAllocateHeap
0x180009716  nop     dword ptr [rax+rax+00h]
0x18000971b  mov     rsi, rax
0x18000971e  mov     [rsp+88h+var_48], rax
0x180009723  test    rax, rax
0x180009726  jz      loc_180009A6C
0x18000972c  xor     edx, edx; Val
0x18000972e  mov     r8d, 248h; Size
0x180009734  mov     rcx, rax; void *
0x180009737  call    memset_0
0x18000973c  mov     dword ptr [rsi], 248h
0x180009742  mov     dword ptr [rsi+4], 4B53504Bh
0x180009749  mov     [rsi+18h], r15d
0x18000974d  mov     dword ptr [rsi+28h], 0FFFFFFh
0x180009754  mov     eax, [rsp+88h+arg_40]
0x18000975b  mov     [rsi+20Ch], eax
0x180009761  mov     ecx, [rsp+88h+arg_28]
0x180009768  mov     [rsi+210h], ecx
0x18000976e  mov     eax, [rsp+88h+arg_30]
0x180009775  mov     [rsi+214h], eax
0x18000977b  mov     eax, [rsp+88h+arg_38]
0x180009782  mov     [rsi+218h], eax
0x180009788  xor     r12d, r12d
0x18000978b  mov     [rsi+60h], r12
0x18000978f  mov     eax, r12d
0x180009792  test    ecx, ecx
0x180009794  setz    al
0x180009797  mov     [rsi+21Ch], eax
0x18000979d  test    rbx, rbx
0x1800097a0  jz      short loc_1800097AC
0x1800097a2  mov     [rsi+40h], rbx
0x1800097a6  mov     eax, [rbx+3Ch]
0x1800097a9  mov     [rsi+1Ch], eax
0x1800097ac  xorps   xmm0, xmm0
0x1800097af  movups  xmmword ptr [rsi+1B0h], xmm0
0x1800097b6  movups  xmmword ptr [rsi+1C0h], xmm0
0x1800097bd  movups  xmmword ptr [rsi+1D0h], xmm0
0x1800097c4  movups  xmmword ptr [rsi+1E0h], xmm0
0x1800097cb  mov     eax, cs:dword_18007A698
0x1800097d1  test    eax, eax
0x1800097d3  jz      loc_180009A9F
0x1800097d9  mov     eax, cs:g_dwStrongKeyForcePassword
0x1800097df  cmp     eax, 0FFFFFFFFh
0x1800097e2  jz      loc_180009AB9
0x1800097e8  xor     eax, eax
0x1800097ea  mov     [rsi+1F0h], rax
0x1800097f1  mov     [rsi+1A8h], r12d
0x1800097f8  mov     [rsi+1A0h], r12
0x1800097ff  mov     eax, dword ptr [rsp+88h+arg_20]
0x180009806  test    al, 20h
0x180009808  jnz     loc_1800098C5
0x18000980e  bt      eax, 0Eh
0x180009812  jb      loc_180009AC9
0x180009818  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000981f  test    r14, r14
0x180009822  jnz     loc_180009984
0x180009828  mov     dword ptr [rsi+238h], 1
0x180009832  mov     r14, [rsp+88h+Src]
0x18000983a  test    r14, r14
0x18000983d  jnz     loc_180009A2D
0x180009843  test    rdi, rdi
0x180009846  jz      loc_1800098DF
0x18000984c  nop     dword ptr [rax+00h]
0x180009850  lea     rbx, [rbx+1]
0x180009854  cmp     [rdi+rbx*2], r12w
0x180009859  jnz     short loc_180009850
0x18000985b  lea     ebx, ds:2[rbx*2]
0x180009862  mov     rcx, gs:60h
0x18000986b  mov     r8d, ebx; Size
0x18000986e  xor     edx, edx; Flags
0x180009870  mov     rcx, [rcx+30h]; HeapHandle
0x180009874  call    cs:__imp_RtlAllocateHeap
0x18000987b  nop     dword ptr [rax+rax+00h]
0x180009880  mov     [rsi+38h], rax
0x180009884  test    rax, rax
0x180009887  jnz     short loc_1800098D1
0x180009889  mov     ebx, 8009000Eh
0x18000988e  lea     rax, WPP_GLOBAL_Control
0x180009895  mov     rcx, cs:WPP_GLOBAL_Control
0x18000989c  cmp     rcx, rax
0x18000989f  jz      short loc_1800098AB
0x1800098a1  test    byte ptr [rcx+1Ch], 1
0x1800098a5  jnz     loc_180009953
0x1800098ab  test    rsi, rsi
0x1800098ae  jnz     loc_180009B05
0x1800098b4  mov     eax, ebx
0x1800098b6  add     rsp, 58h
0x1800098ba  pop     r15
0x1800098bc  pop     r14
0x1800098be  pop     r12
0x1800098c0  pop     rdi
0x1800098c1  pop     rsi
0x1800098c2  pop     rbx
0x1800098c3  retn
0x1800098c5  mov     dword ptr [rsi+20h], 1
0x1800098cc  jmp     loc_18000980E
0x1800098d1  mov     r8, rbx; Size
0x1800098d4  mov     rdx, rdi; Src
0x1800098d7  mov     rcx, rax; void *
0x1800098da  call    memcpy_0
0x1800098df  lea     rax, [rsi+120h]
0x1800098e6  mov     [rax+8], rax
0x1800098ea  mov     [rax], rax
0x1800098ed  lea     rax, NormalModeBCryptSecretsFuncTable
0x1800098f4  mov     [rsi+0A8h], rax
0x1800098fb  lea     rcx, [rsi+130h]; Resource
0x180009902  call    cs:__imp_RtlInitializeResource
0x180009909  nop     dword ptr [rax+rax+00h]
0x18000990e  jmp     short loc_18000993D
0x180009910  mov     ebx, 8009000Eh
0x180009915  mov     r9d, 46Fh
0x18000991b  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009922  lea     rdx, aStatus; "Status"
0x180009929  mov     ecx, 8009000Eh
0x18000992e  call    DebugTraceError
0x180009933  mov     rsi, [rsp+88h+var_48]
0x180009938  jmp     loc_1800098AB
0x18000993d  mov     rax, [rsp+88h+arg_50]
0x180009945  mov     [rax], rsi
0x180009948  mov     rsi, r12
0x18000994b  mov     ebx, r12d
0x18000994e  jmp     loc_1800098AB
0x180009953  mov     dword ptr [rsp+88h+var_58], 45Eh
0x18000995b  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009962  mov     [rsp+88h+var_60], rax
0x180009967  mov     [rsp+88h+var_68], 8009000Eh
0x18000996f  lea     r9, aStatus; "Status"
0x180009976  mov     rcx, [rcx+10h]
0x18000997a  call    WPP_SF_sDsd
0x18000997f  jmp     loc_1800098AB
0x180009984  mov     rax, rbx
0x180009987  nop     word ptr [rax+rax+00000000h]
0x180009990  inc     rax
0x180009993  cmp     [r14+rax*2], r12w
0x180009998  jnz     short loc_180009990
0x18000999a  inc     eax
0x18000999c  cmp     eax, 104h
0x1800099a1  ja      short loc_1800099E6
0x1800099a3  add     eax, eax
0x1800099a5  mov     r15d, eax
0x1800099a8  mov     rcx, gs:60h
0x1800099b1  mov     r8d, eax; Size
0x1800099b4  xor     edx, edx; Flags
0x1800099b6  mov     rcx, [rcx+30h]; HeapHandle
0x1800099ba  call    cs:__imp_RtlAllocateHeap
0x1800099c1  nop     dword ptr [rax+rax+00h]
0x1800099c6  mov     [rsi+8], rax
0x1800099ca  test    rax, rax
0x1800099cd  jz      loc_180009AD5
0x1800099d3  mov     r8d, r15d; Size
0x1800099d6  mov     rdx, r14; Src
0x1800099d9  mov     rcx, rax; void *
0x1800099dc  call    memcpy_0
0x1800099e1  jmp     loc_180009832
0x1800099e6  mov     ebx, 80090027h
0x1800099eb  lea     rax, WPP_GLOBAL_Control
0x1800099f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800099f9  cmp     rcx, rax
0x1800099fc  jz      loc_1800098AB
0x180009a02  test    byte ptr [rcx+1Ch], 1
0x180009a06  jz      loc_1800098AB
0x180009a0c  mov     dword ptr [rsp+88h+var_58], 42Ah
0x180009a14  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009a1b  mov     [rsp+88h+var_60], rax
0x180009a20  mov     [rsp+88h+var_68], 80090027h
0x180009a28  jmp     loc_18000996F
0x180009a2d  mov     rax, rbx
0x180009a30  lea     rax, [rax+1]
0x180009a34  cmp     [r14+rax*2], r12w
0x180009a39  jnz     short loc_180009A30
0x180009a3b  lea     eax, ds:2[rax*2]
0x180009a42  mov     r15d, eax
0x180009a45  mov     ecx, eax
0x180009a47  call    SafeAllocaAllocateFromHeap
0x180009a4c  mov     [rsi+50h], rax
0x180009a50  test    rax, rax
0x180009a53  jz      loc_180009ADD
0x180009a59  mov     r8d, r15d; Size
0x180009a5c  mov     rdx, r14; Src
0x180009a5f  mov     rcx, rax; void *
0x180009a62  call    memcpy_0
0x180009a67  jmp     loc_180009843
0x180009a6c  mov     ebx, 8009000Eh
0x180009a71  lea     rax, WPP_GLOBAL_Control
0x180009a78  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a7f  cmp     rcx, rax
0x180009a82  jz      loc_1800098AB
0x180009a88  test    byte ptr [rcx+1Ch], 1
0x180009a8c  jz      loc_1800098AB
0x180009a92  mov     dword ptr [rsp+88h+var_58], 3DBh
0x180009a9a  jmp     loc_18000995B
0x180009a9f  call    KspInitStrongKeyCacheDuration
0x180009aa4  mov     cs:g_dwStrongKeyCacheDuration, eax
0x180009aaa  mov     cs:dword_18007A698, 1
0x180009ab4  jmp     loc_1800097D9
0x180009ab9  call    KspInitStrongKeyForcePassword
0x180009abe  mov     cs:g_dwStrongKeyForcePassword, eax
0x180009ac4  jmp     loc_1800097E8
0x180009ac9  or      dword ptr [rsi+1ACh], 40h
0x180009ad0  jmp     loc_180009818
0x180009ad5  mov     r9d, 435h
0x180009adb  jmp     short loc_180009AE3
0x180009add  mov     r9d, 44Fh
0x180009ae3  mov     ebx, 8009000Eh
0x180009ae8  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009aef  lea     rdx, aStatus; "Status"
0x180009af6  mov     ecx, 8009000Eh
0x180009afb  call    DebugTraceError
0x180009b00  jmp     loc_1800098AB
0x180009b05  mov     rcx, [rsi+1A0h]
0x180009b0c  test    rcx, rcx
0x180009b0f  jz      short loc_180009B16
0x180009b11  call    MSCryptFree
0x180009b16  mov     rcx, [rsi+8]
0x180009b1a  test    rcx, rcx
0x180009b1d  jz      short loc_180009B24
0x180009b1f  call    MSCryptFree
0x180009b24  mov     rcx, [rsi+38h]
0x180009b28  test    rcx, rcx
0x180009b2b  jz      short loc_180009B32
0x180009b2d  call    MSCryptFree
0x180009b32  mov     rcx, [rsi+50h]
0x180009b36  test    rcx, rcx
0x180009b39  jz      short loc_180009B40
0x180009b3b  call    MSCryptFree
0x180009b40  mov     rcx, rsi
0x180009b43  call    MSCryptFree
0x180009b48  jmp     loc_1800098B4
```
