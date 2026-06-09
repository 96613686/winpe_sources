# Smb2Read_Start

- ea: `0x14001a2b0`
- end: `0x14001a6d6`
- name: `Smb2Read_Start`
- size: `1062`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x14000b940`
- `0x14001a2b0`
- `0x14001a6e0`
- `0x14001a8d0`
- `0x14002e258`

## import_xrefs

- `mrxsmb!RDR_PERF_INIT` at `0x14001a4f5`
- `mrxsmb!RDR_PERF_INIT` at `0x14001a4f5`
- `mrxsmb!SmbCseEstimateMemoryDescriptorSize` at `0x14001a67e`
- `mrxsmb!SmbCseEstimateMemoryDescriptorSize` at `0x14001a67e`
- `mrxsmb!SmbCeQueryOptimalBufferSize` at `0x14001a3e5`
- `mrxsmb!SmbCeQueryOptimalBufferSize` at `0x14001a3e5`
- `mrxsmb!RDR_PERF_ENTER` at `0x14001a308`
- `mrxsmb!RDR_PERF_ENTER` at `0x14001a48e`
- `mrxsmb!RDR_PERF_ENTER` at `0x14001a308`
- `mrxsmb!RDR_PERF_ENTER` at `0x14001a48e`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14001a349`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14001a35a`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14001a349`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14001a35a`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x14001a504`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x14001a504`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x14001a6a6`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x14001a6a6`

## pseudocode

```c
__int64 __fastcall Smb2Read_Start(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  char v4; // r14
  __int64 v5; // rdi
  __int64 v6; // rax
  __int64 v7; // rbp
  __int64 v8; // rcx
  ULONG v9; // r15d
  __int64 v10; // r13
  __int64 v11; // rcx
  __int64 v12; // rdi
  __int64 v13; // r8
  __int64 result; // rax
  int BuildChunk; // edi
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  int v21; // esi
  unsigned int v22; // r14d
  ULONG Length; // ebp
  __int64 v24; // r8
  __int64 v25; // rsi
  __int64 v26; // rcx
  unsigned int v27; // ecx
  char v28; // al
  unsigned int v29; // ecx
  int v30; // [rsp+50h] [rbp-68h] BYREF
  int v31[2]; // [rsp+58h] [rbp-60h] BYREF
  __int64 v32; // [rsp+60h] [rbp-58h]
  char v33; // [rsp+C0h] [rbp+8h]
  unsigned __int16 v34; // [rsp+C8h] [rbp+10h] BYREF
  unsigned int v35; // [rsp+D0h] [rbp+18h] BYREF
  int v36; // [rsp+D8h] [rbp+20h]

  v2 = *(_QWORD *)(a1 + 48);
  LOBYTE(a2) = 15;
  v4 = 0;
  v5 = *(_QWORD *)(a1 + 2464);
  v6 = *(_QWORD *)(*(_QWORD *)(v2 + 72) + 48LL);
  v35 = 0;
  v32 = v6;
  v7 = *(_QWORD *)(*(_QWORD *)(a1 + 96) + 392LL);
  v30 = 0;
  v34 = 0;
  RDR_PERF_ENTER(a1 + 512, a2);
  if ( v5 )
  {
    v9 = *(_DWORD *)(v5 + 12);
  }
  else
  {
    v9 = *(_DWORD *)(v2 + 568);
    v5 = v2 + 560;
  }
  v10 = *(_QWORD *)v5;
  if ( *(_DWORD *)MRxSmbGetConfigurationBlock(v8)
    && v9 >= *(_DWORD *)MRxSmbGetConfigurationBlock(v11)
    && (unsigned int)(*(_DWORD *)(v7 + 320) - 2) <= 1
    && !*(_QWORD *)(a1 + 56) )
  {
    v12 = *(_QWORD *)(a1 + 72);
    v13 = *(_QWORD *)(*(_QWORD *)(a1 + 88) + 424LL);
    if ( (*(_DWORD *)(a1 + 68) & 0x1000000) != 0 && (*(_DWORD *)(v12 + 748) & 1) == 0 )
    {
      v29 = *(_DWORD *)(v12 + 584);
      if ( v29 != 144 * (v29 / 0x90) )
        goto LABEL_10;
      if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x8000000) != 0 )
      {
        McTemplateK0hzr0_EtwWriteTransfer(
          v29,
          (unsigned int)RdmaWithEncryption,
          v13,
          *(_WORD *)(v13 + 96) >> 1,
          *(_QWORD *)(v13 + 104));
        _InterlockedIncrement((volatile signed __int32 *)(v12 + 584));
        goto LABEL_10;
      }
      goto LABEL_51;
    }
    if ( (*(_DWORD *)(a1 + 68) & 0x800) == 0 || (*(_DWORD *)(v12 + 748) & 2) != 0 )
    {
      v4 = 1;
      goto LABEL_10;
    }
    v27 = *(_DWORD *)(v12 + 584);
    if ( v27 == 144 * (v27 / 0x90) )
    {
      if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x8000000) != 0 )
        McTemplateK0hzr0_EtwWriteTransfer(
          v27,
          (unsigned int)RdmaWithSigning,
          v13,
          *(_WORD *)(v13 + 96) >> 1,
          *(_QWORD *)(v13 + 104));
LABEL_51:
      _InterlockedIncrement((volatile signed __int32 *)(v12 + 584));
    }
  }
LABEL_10:
  result = AllocateReadBufferDescriptors(a1, v4);
  BuildChunk = result;
  if ( (int)result >= 0 )
  {
    v16 = *(_QWORD *)(a1 + 96);
    v33 = 0;
    v36 = 0;
    SmbCeQueryOptimalBufferSize(v16, 0, &v35, 0);
    if ( !v4 && *(_DWORD *)(v7 + 320) == 2 )
    {
      v19 = v35;
      if ( v35 >= *(_DWORD *)(v7 + 112) )
      {
        v19 = *(_DWORD *)(v7 + 112);
        v35 = v19;
      }
    }
    else
    {
      v19 = v35;
    }
    if ( v19 < 0x10000 )
    {
      v19 = 0x10000;
      v35 = 0x10000;
    }
    if ( v4 )
    {
      SmbCseEstimateMemoryDescriptorSize(
        v7,
        v9,
        (*(_BYTE *)(*(_QWORD *)(a1 + 72) + 736LL) & 0x40) != 0,
        &v35,
        &v34,
        &v30);
      v19 = v35;
    }
    v20 = v19 & 0xFFFF0000;
    v35 = v20;
    if ( (*(_DWORD *)(v2 + 120) & 0x1000000) != 0 )
    {
      LOWORD(v18) = 2;
      LOWORD(v17) = 3;
      v28 = SmbCeCheckServerEntryDialect(*(_QWORD *)(a1 + 72), v17, 0, v18);
      v21 = v36;
      if ( v28 )
        v21 = 1;
      v20 = v35;
      v36 = v21;
    }
    else
    {
      LOBYTE(v21) = v36;
    }
    v22 = 0;
    while ( v9 )
    {
      *(_QWORD *)v31 = 0;
      Length = v9;
      LOBYTE(v17) = 17;
      if ( v20 < v9 )
        Length = v20;
      RDR_PERF_ENTER(a1 + 512, v17);
      BuildChunk = Smb2Read_BuildChunk((__int64 *)v31, a1, (__int128 *)(v32 + 28), v10, v22, Length, v30, v34, v21);
      if ( BuildChunk < 0 )
        break;
      v25 = *(_QWORD *)v31;
      LOBYTE(v24) = 24;
      v26 = *(_QWORD *)v31;
      *(_WORD *)(*(_QWORD *)v31 + 2LL) = 8;
      RDR_PERF_INIT(v26, 58144, v24);
      BuildChunk = SmbCseSubmitBufferContext(v25);
      if ( BuildChunk < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          if ( BYTE1(WPP_GLOBAL_Control->Timer) )
            WPP_SF_DiqD(
              WPP_GLOBAL_Control->AttachedDevice,
              14,
              (unsigned int)WPP_a0b49660c994371bf323b193efb7fcea_Traceguids,
              Length,
              v22,
              v25,
              BuildChunk);
        }
        break;
      }
      if ( *(_BYTE *)(a1 + 1040) == 1 )
        return 259;
      v20 = v35;
      v9 -= Length;
      LOBYTE(v21) = v36;
      v22 += Length;
      v33 = 1;
    }
    if ( !v33 )
      return (unsigned int)BuildChunk;
    return 259;
  }
  return result;
}

```

## disassembly

```asm
0x14001a2b0  push    rbx
0x14001a2b2  push    rbp
0x14001a2b3  push    rsi
0x14001a2b4  push    rdi
0x14001a2b5  push    r12
0x14001a2b7  push    r13
0x14001a2b9  push    r14
0x14001a2bb  push    r15
0x14001a2bd  sub     rsp, 78h
0x14001a2c1  mov     rsi, [rcx+30h]
0x14001a2c5  mov     rbx, rcx
0x14001a2c8  xor     ecx, ecx
0x14001a2ca  mov     dl, 0Fh
0x14001a2cc  xor     r14b, r14b
0x14001a2cf  mov     rax, [rsi+48h]
0x14001a2d3  mov     rdi, [rbx+9A0h]
0x14001a2da  mov     rax, [rax+30h]
0x14001a2de  mov     [rsp+0B8h+arg_10], ecx
0x14001a2e5  mov     [rsp+0B8h+var_58], rax
0x14001a2ea  mov     rax, [rbx+60h]
0x14001a2ee  mov     rbp, [rax+188h]
0x14001a2f5  mov     [rsp+0B8h+var_68], ecx
0x14001a2f9  mov     [rsp+0B8h+arg_8], cx
0x14001a301  lea     rcx, [rbx+200h]
0x14001a308  call    cs:__imp_RDR_PERF_ENTER
0x14001a30f  nop     dword ptr [rax+rax+00h]
0x14001a314  test    rdi, rdi
0x14001a317  jnz     loc_14001A46A
0x14001a31d  mov     r15d, [rsi+238h]
0x14001a324  lea     rdi, [rsi+230h]
0x14001a32b  mov     eax, [rbp+140h]
0x14001a331  mov     r13, [rdi]
0x14001a334  sub     eax, 2
0x14001a337  lea     rdi, [rbx+38h]
0x14001a33b  cmp     eax, 1
0x14001a33e  ja      short loc_14001A349
0x14001a340  cmp     qword ptr [rdi], 0
0x14001a344  jnz     short loc_14001A349
0x14001a346  mov     eax, [rbx+44h]
0x14001a349  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14001a350  nop     dword ptr [rax+rax+00h]
0x14001a355  cmp     dword ptr [rax], 0
0x14001a358  jbe     short loc_14001A3AB
0x14001a35a  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14001a361  nop     dword ptr [rax+rax+00h]
0x14001a366  cmp     r15d, [rax]
0x14001a369  jb      short loc_14001A3AB
0x14001a36b  mov     eax, [rbp+140h]
0x14001a371  sub     eax, 2
0x14001a374  cmp     eax, 1
0x14001a377  ja      short loc_14001A3AB
0x14001a379  cmp     qword ptr [rdi], 0
0x14001a37d  jnz     short loc_14001A3AB
0x14001a37f  mov     rax, [rbx+58h]
0x14001a383  mov     rdi, [rbx+48h]
0x14001a387  mov     r8, [rax+1A8h]
0x14001a38e  mov     eax, [rbx+44h]
0x14001a391  bt      eax, 18h
0x14001a395  jb      loc_14001A5A4
0x14001a39b  mov     eax, [rbx+44h]
0x14001a39e  bt      eax, 0Bh
0x14001a3a2  jb      loc_14001A5B7
0x14001a3a8  mov     r14b, 1
0x14001a3ab  movzx   edx, r14b
0x14001a3af  mov     rcx, rbx
0x14001a3b2  call    AllocateReadBufferDescriptors
0x14001a3b7  mov     edi, eax
0x14001a3b9  test    eax, eax
0x14001a3bb  js      loc_14001A458
0x14001a3c1  mov     rcx, [rbx+60h]
0x14001a3c5  lea     r8, [rsp+0B8h+arg_10]
0x14001a3cd  xor     r9d, r9d
0x14001a3d0  mov     [rsp+0B8h+arg_0], 0
0x14001a3d8  xor     edx, edx
0x14001a3da  mov     [rsp+0B8h+arg_18], 0
0x14001a3e5  call    cs:__imp_SmbCeQueryOptimalBufferSize
0x14001a3ec  nop     dword ptr [rax+rax+00h]
0x14001a3f1  test    r14b, r14b
0x14001a3f4  jnz     short loc_14001A403
0x14001a3f6  cmp     dword ptr [rbp+140h], 2
0x14001a3fd  jz      loc_14001A614
0x14001a403  mov     ecx, [rsp+0B8h+arg_10]
0x14001a40a  cmp     ecx, 10000h
0x14001a410  jb      loc_14001A634
0x14001a416  test    r14b, r14b
0x14001a419  jnz     loc_14001A645
0x14001a41f  and     ecx, 0FFFF0000h
0x14001a425  mov     [rsp+0B8h+arg_10], ecx
0x14001a42c  test    dword ptr [rsi+78h], 1000000h
0x14001a433  jnz     loc_14001A696
0x14001a439  mov     esi, [rsp+0B8h+arg_18]
0x14001a440  xor     r14d, r14d
0x14001a443  test    r15d, r15d
0x14001a446  jnz     short loc_14001A473
0x14001a448  cmp     [rsp+0B8h+arg_0], 0
0x14001a450  jnz     loc_14001A51F
0x14001a456  mov     eax, edi
0x14001a458  add     rsp, 78h
0x14001a45c  pop     r15
0x14001a45e  pop     r14
0x14001a460  pop     r13
0x14001a462  pop     r12
0x14001a464  pop     rdi
0x14001a465  pop     rsi
0x14001a466  pop     rbp
0x14001a467  pop     rbx
0x14001a468  retn
0x14001a46a  mov     r15d, [rdi+0Ch]
0x14001a46e  jmp     loc_14001A32B
0x14001a473  cmp     ecx, r15d
0x14001a476  mov     qword ptr [rsp+0B8h+var_60], 0
0x14001a47f  mov     ebp, r15d
0x14001a482  mov     dl, 11h
0x14001a484  cmovb   ebp, ecx
0x14001a487  lea     rcx, [rbx+200h]
0x14001a48e  call    cs:__imp_RDR_PERF_ENTER
0x14001a495  nop     dword ptr [rax+rax+00h]
0x14001a49a  movzx   eax, [rsp+0B8h+arg_8]
0x14001a4a2  lea     rcx, [rsp+0B8h+var_60]; int
0x14001a4a7  mov     r8, [rsp+0B8h+var_58]
0x14001a4ac  mov     r9, r13; int
0x14001a4af  mov     [rsp+0B8h+var_78], esi; int
0x14001a4b3  add     r8, 1Ch; int
0x14001a4b7  mov     [rsp+0B8h+var_80], ax; __int16
0x14001a4bc  mov     rdx, rbx; int
0x14001a4bf  mov     eax, [rsp+0B8h+var_68]
0x14001a4c3  mov     [rsp+0B8h+var_88], eax; int
0x14001a4c7  mov     [rsp+0B8h+Length], ebp; Length
0x14001a4cb  mov     [rsp+0B8h+var_98], r14d; int
0x14001a4d0  call    Smb2Read_BuildChunk
0x14001a4d5  mov     edi, eax
0x14001a4d7  test    eax, eax
0x14001a4d9  js      loc_14001A448
0x14001a4df  mov     rsi, qword ptr [rsp+0B8h+var_60]
0x14001a4e4  mov     edx, 0E320h
0x14001a4e9  mov     r8b, 18h
0x14001a4ec  mov     rcx, rsi
0x14001a4ef  mov     word ptr [rsi+2], 8
0x14001a4f5  call    cs:__imp_RDR_PERF_INIT
0x14001a4fc  nop     dword ptr [rax+rax+00h]
0x14001a501  mov     rcx, rsi
0x14001a504  call    cs:__imp_SmbCseSubmitBufferContext
0x14001a50b  nop     dword ptr [rax+rax+00h]
0x14001a510  mov     edi, eax
0x14001a512  test    eax, eax
0x14001a514  js      short loc_14001A54A
0x14001a516  cmp     byte ptr [rbx+410h], 1
0x14001a51d  jnz     short loc_14001A529
0x14001a51f  mov     eax, 103h
0x14001a524  jmp     loc_14001A458
0x14001a529  mov     ecx, [rsp+0B8h+arg_10]
0x14001a530  sub     r15d, ebp
0x14001a533  mov     esi, [rsp+0B8h+arg_18]
0x14001a53a  add     r14d, ebp
0x14001a53d  mov     [rsp+0B8h+arg_0], 1
0x14001a545  jmp     loc_14001A443
0x14001a54a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a551  lea     rax, WPP_GLOBAL_Control
0x14001a558  cmp     rcx, rax
0x14001a55b  jz      loc_14001A448
0x14001a561  mov     eax, [rcx+2Ch]
0x14001a564  test    al, 1
0x14001a566  jz      loc_14001A448
0x14001a56c  cmp     byte ptr [rcx+29h], 1
0x14001a570  jb      loc_14001A448
0x14001a576  mov     rcx, [rcx+18h]
0x14001a57a  lea     r8, WPP_a0b49660c994371bf323b193efb7fcea_Traceguids
0x14001a581  mov     eax, r14d
0x14001a584  mov     edx, 0Eh
0x14001a589  mov     [rsp+0B8h+var_88], edi
0x14001a58d  mov     r9d, ebp
0x14001a590  mov     qword ptr [rsp+0B8h+Length], rsi
0x14001a595  mov     qword ptr [rsp+0B8h+var_98], rax
0x14001a59a  call    WPP_SF_DiqD
0x14001a59f  jmp     loc_14001A448
0x14001a5a4  mov     eax, [rdi+2ECh]
0x14001a5aa  test    al, 1
0x14001a5ac  jnz     loc_14001A39B
0x14001a5b2  jmp     loc_14003B938
0x14001a5b7  mov     eax, [rdi+2ECh]
0x14001a5bd  test    al, 2
0x14001a5bf  jnz     loc_14001A3A8
0x14001a5c5  mov     ecx, [rdi+248h]
0x14001a5cb  mov     eax, 38E38E39h
0x14001a5d0  mul     ecx
0x14001a5d2  shr     edx, 5
0x14001a5d5  lea     eax, [rdx+rdx*8]
0x14001a5d8  shl     eax, 4
0x14001a5db  cmp     ecx, eax
0x14001a5dd  jnz     loc_14001A3AB
0x14001a5e3  test    byte ptr cs:WPP_MAIN_CB.Queue+13h, 8
0x14001a5ea  jz      loc_14003B989
0x14001a5f0  movzx   r9d, word ptr [r8+60h]
0x14001a5f5  lea     rdx, RdmaWithSigning
0x14001a5fc  mov     rax, [r8+68h]
0x14001a600  shr     r9w, 1
0x14001a604  mov     qword ptr [rsp+0B8h+var_98], rax
0x14001a609  call    McTemplateK0hzr0_EtwWriteTransfer
0x14001a60e  nop
0x14001a60f  jmp     loc_14003B989
0x14001a614  mov     eax, [rbp+70h]
0x14001a617  mov     ecx, [rsp+0B8h+arg_10]
0x14001a61e  cmp     ecx, eax
0x14001a620  jb      loc_14001A40A
0x14001a626  mov     ecx, eax
0x14001a628  mov     [rsp+0B8h+arg_10], eax
0x14001a62f  jmp     loc_14001A40A
0x14001a634  mov     ecx, 10000h
0x14001a639  mov     [rsp+0B8h+arg_10], ecx
0x14001a640  jmp     loc_14001A416
0x14001a645  mov     rax, [rbx+48h]
0x14001a649  lea     r9, [rsp+0B8h+arg_10]
0x14001a651  mov     edx, r15d
0x14001a654  mov     rcx, rbp
0x14001a657  movzx   r8d, byte ptr [rax+2E0h]
0x14001a65f  lea     rax, [rsp+0B8h+var_68]
0x14001a664  mov     qword ptr [rsp+0B8h+Length], rax
0x14001a669  lea     rax, [rsp+0B8h+arg_8]
0x14001a671  shr     r8b, 6
0x14001a675  and     r8b, 1
0x14001a679  mov     qword ptr [rsp+0B8h+var_98], rax
0x14001a67e  call    cs:__imp_SmbCseEstimateMemoryDescriptorSize
0x14001a685  nop     dword ptr [rax+rax+00h]
0x14001a68a  mov     ecx, [rsp+0B8h+arg_10]
0x14001a691  jmp     loc_14001A41F
0x14001a696  mov     rcx, [rbx+48h]
0x14001a69a  mov     r9w, 2
0x14001a69f  xor     r8d, r8d
0x14001a6a2  mov     dx, 3
0x14001a6a6  call    cs:__imp_SmbCeCheckServerEntryDialect
0x14001a6ad  nop     dword ptr [rax+rax+00h]
0x14001a6b2  mov     esi, [rsp+0B8h+arg_18]
0x14001a6b9  mov     ecx, 1
0x14001a6be  test    al, al
0x14001a6c0  cmovnz  esi, ecx
0x14001a6c3  mov     ecx, [rsp+0B8h+arg_10]
0x14001a6ca  mov     [rsp+0B8h+arg_18], esi
0x14001a6d1  jmp     loc_14001A440
0x14003b938  mov     ecx, [rdi+248h]
0x14003b93e  mov     eax, 38E38E39h
0x14003b943  mul     ecx
0x14003b945  shr     edx, 5
0x14003b948  lea     eax, [rdx+rdx*8]
0x14003b94b  shl     eax, 4
0x14003b94e  cmp     ecx, eax
0x14003b950  jnz     loc_14001A3AB
0x14003b956  test    byte ptr cs:WPP_MAIN_CB.Queue+13h, 8
0x14003b95d  jz      short loc_14003B989
0x14003b95f  movzx   r9d, word ptr [r8+60h]
0x14003b964  lea     rdx, RdmaWithEncryption
0x14003b96b  mov     rax, [r8+68h]
0x14003b96f  shr     r9w, 1
0x14003b973  mov     qword ptr [rsp+0B8h+var_98], rax
0x14003b978  call    McTemplateK0hzr0_EtwWriteTransfer
0x14003b97d  lock inc dword ptr [rdi+248h]
0x14003b984  jmp     loc_14001A3AB
0x14003b989  lock inc dword ptr [rdi+248h]
0x14003b990  jmp     loc_14001A3AB
```
