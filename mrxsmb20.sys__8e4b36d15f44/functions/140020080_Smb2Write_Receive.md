# Smb2Write_Receive

- ea: `0x140020080`
- end: `0x140020482`
- name: `Smb2Write_Receive`
- size: `1026`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, int, _DWORD *, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callees

- `0x14000fa00`
- `0x140015570`
- `0x14001e470`
- `0x140020080`
- `0x1400297fc`
- `0x14002a9ac`
- `0x140036950`

## import_xrefs

- `mrxsmb!RDR_PERF_FREE` at `0x1400203dd`
- `mrxsmb!RDR_PERF_FREE` at `0x1400203dd`
- `mrxsmb!RDR_PERF_OUTPUT_ETW` at `0x1400203ca`
- `mrxsmb!RDR_PERF_OUTPUT_ETW` at `0x1400203ca`
- `mrxsmb!RDR_PERF_EXIT` at `0x1400203b7`
- `mrxsmb!RDR_PERF_EXIT` at `0x1400203b7`
- `mrxsmb!RDR_PERF_ENTER` at `0x1400200ec`
- `mrxsmb!RDR_PERF_ENTER` at `0x1400200ec`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14002035d`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14002035d`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x140020407`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x140020407`

## pseudocode

```c
__int64 __fastcall Smb2Write_Receive(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        _DWORD *a6,
        __int64 a7)
{
  unsigned int LockArray_high; // r12d
  int v9; // r15d
  unsigned __int64 v11; // rbp
  __int64 v12; // rdi
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rax
  unsigned int v17; // r13d
  int v18; // edi
  __int64 v19; // rcx
  unsigned int v20; // edi
  PDEVICE_OBJECT v21; // rcx
  __int64 v22; // rdx
  unsigned int v23; // r8d
  unsigned __int64 v24; // rcx
  unsigned int i; // eax
  __int64 v26; // rdi
  unsigned __int8 *v28; // [rsp+30h] [rbp-48h] BYREF
  __int64 v29; // [rsp+88h] [rbp+10h] BYREF
  __int64 v30; // [rsp+90h] [rbp+18h]

  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  v9 = *(_DWORD *)(a3 + 16);
  v11 = a4;
  v12 = *(_QWORD *)(a2 + 760);
  v13 = *(_QWORD *)(a1 + 88);
  v30 = 0;
  v14 = a2 + 880;
  v15 = *(_QWORD *)(v13 + 424);
  v16 = *(_QWORD *)(v15 + 1480);
  v17 = *(_DWORD *)(v15 + 1488);
  LOBYTE(v15) = 35;
  v29 = v16;
  RDR_PERF_ENTER(v14, v15);
  if ( v9 >= 0 )
  {
    if ( (unsigned __int64)(unsigned int)(16 * *(_DWORD *)(a2 + 1420)) + 64 > v11 )
    {
      *a6 = a5;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        v22 = 22;
LABEL_17:
        WPP_SF_q(v21->AttachedDevice, v22, WPP_37fe073fcb403a48ea10fb83da93c962_Traceguids, a1);
      }
LABEL_18:
      v9 = -1073741629;
      goto LABEL_41;
    }
    v23 = 0;
    v24 = a7 + 64;
    for ( i = 0; i < *(_DWORD *)(a2 + 1420); ++i )
    {
      if ( *(_WORD *)v24 != 17 )
      {
        *a6 = a5;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_37fe073fcb403a48ea10fb83da93c962_Traceguids);
          v9 = -1073741629;
          goto LABEL_41;
        }
        goto LABEL_18;
      }
      v23 += *(_DWORD *)(v24 + 4);
      v24 += 16LL;
    }
    if ( v12 )
    {
      if ( v23 <= *(_DWORD *)(a2 + 776) )
      {
LABEL_29:
        *(_DWORD *)(a2 + 748) = v23;
        v26 = v29 + 192LL * (LockArray_high % v17);
        if ( *(_DWORD *)(a1 + 1052) == 1 )
        {
          if ( *(_BYTE *)(a1 + 1056) )
          {
            if ( (*(_DWORD *)(a1 + 68) & 0x1000800) == 0 )
            {
              if ( *(_DWORD *)(*(_QWORD *)(a1 + 72) + 632LL) <= 1u
                || (v24 = *(_QWORD *)(a1 + 200) % 0x23C34600uLL, v24 >= 0x4C4B40) )
              {
                _InterlockedOr((volatile signed __int32 *)(a1 + 68), 0x100000u);
              }
            }
          }
        }
        if ( (*(_BYTE *)(MRxSmbGetConfigurationBlock(v24) + 64) & 1) != 0 && *(_QWORD *)(a2 + 848) )
          Smb2Write_UpdatePerfCounters(v26, a2);
        if ( *(_BYTE *)(a2 + 856) )
        {
          _InterlockedDecrement((volatile signed __int32 *)(v26 + 88));
          *(_BYTE *)(a2 + 856) = 0;
        }
        *a6 = a5;
        goto LABEL_41;
      }
    }
    else if ( v23 <= *(_DWORD *)(a2 + 744) )
    {
      goto LABEL_29;
    }
    *a6 = a5;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v22 = 24;
      goto LABEL_17;
    }
    goto LABEL_18;
  }
  if ( !*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 72) + 24LL) + 1313LL) )
  {
    *a6 = a5;
LABEL_41:
    v20 = 0;
    goto LABEL_42;
  }
  v18 = a5;
  if ( (_DWORD)v11 == a5 )
  {
    v28 = 0;
    LODWORD(v29) = 0;
    if ( (int)Smb2QueryErrorDataFromResponse(a7 + 64, (int)v11 - 64, 1164730963, &v28, (unsigned int *)&v29) >= 0 )
    {
      v19 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 40LL);
      if ( v19 )
      {
        if ( v28 && (unsigned int)v29 >= 8 )
          StRtlIoStorInfoSetSenseCode(v19, v28[4], v28[5], v28[6]);
      }
    }
    *a6 = v18;
    goto LABEL_41;
  }
  v20 = Smb2BufferErrorResponse(a2, a7, v11, a5, (__int64)a6);
LABEL_42:
  RDR_PERF_EXIT(a2 + 880);
  RDR_PERF_OUTPUT_ETW(a2 + 880);
  RDR_PERF_FREE(a2 + 880);
  v30 = (unsigned int)v9;
  SmbCseUpdateBufferContextStatus(a2, (unsigned int)v9);
  return v20;
}

```

## disassembly

```asm
0x140020080  mov     [rsp+arg_18], rbx
0x140020085  push    rbp
0x140020086  push    rsi
0x140020087  push    rdi
0x140020088  push    r12
0x14002008a  push    r13
0x14002008c  push    r14
0x14002008e  push    r15
0x140020090  sub     rsp, 40h
0x140020094  mov     r12d, gs:1A4h
0x14002009d  mov     rbx, rdx
0x1400200a0  mov     r15d, [r8+10h]
0x1400200a4  mov     r14, rcx
0x1400200a7  xor     ecx, ecx
0x1400200a9  mov     ebp, r9d
0x1400200ac  mov     [rsp+78h+arg_0], ecx
0x1400200b3  mov     rdi, [rbx+2F8h]
0x1400200ba  mov     rax, [r14+58h]
0x1400200be  mov     [rsp+78h+arg_10], rcx
0x1400200c6  lea     rcx, [rbx+370h]
0x1400200cd  mov     rdx, [rax+1A8h]
0x1400200d4  mov     rax, [rdx+5C8h]
0x1400200db  mov     r13d, [rdx+5D0h]
0x1400200e2  mov     dl, 23h ; '#'
0x1400200e4  mov     [rsp+78h+arg_8], rax
0x1400200ec  call    cs:__imp_RDR_PERF_ENTER
0x1400200f3  nop     dword ptr [rax+rax+00h]
0x1400200f8  test    r15d, r15d
0x1400200fb  jns     loc_1400201E8
0x140020101  mov     rax, [r14+48h]
0x140020105  mov     rcx, [rax+18h]
0x140020109  cmp     byte ptr [rcx+521h], 0
0x140020110  jnz     short loc_140020128
0x140020112  mov     rcx, [rsp+78h+arg_28]
0x14002011a  mov     eax, [rsp+78h+arg_20]
0x140020121  mov     [rcx], eax
0x140020123  jmp     loc_1400203A9
0x140020128  mov     edi, [rsp+78h+arg_20]
0x14002012f  cmp     ebp, edi
0x140020131  jnz     loc_1400201BE
0x140020137  mov     rcx, [rsp+78h+arg_30]
0x14002013f  lea     rax, [rsp+78h+arg_8]
0x140020147  add     rcx, 40h ; '@'
0x14002014b  mov     [rsp+78h+var_48], 0
0x140020154  lea     edx, [rbp-40h]
0x140020157  mov     dword ptr [rsp+78h+arg_8], 0
0x140020162  lea     r9, [rsp+78h+var_48]
0x140020167  mov     [rsp+78h+var_58], rax
0x14002016c  mov     r8d, 456C6253h
0x140020172  call    Smb2QueryErrorDataFromResponse
0x140020177  test    eax, eax
0x140020179  js      short loc_1400201AF
0x14002017b  mov     rax, [r14+30h]
0x14002017f  mov     rcx, [rax+28h]
0x140020183  test    rcx, rcx
0x140020186  jz      short loc_1400201AF
0x140020188  mov     rdx, [rsp+78h+var_48]
0x14002018d  test    rdx, rdx
0x140020190  jz      short loc_1400201AF
0x140020192  cmp     dword ptr [rsp+78h+arg_8], 8
0x14002019a  jb      short loc_1400201AF
0x14002019c  movzx   r9d, byte ptr [rdx+6]
0x1400201a1  movzx   r8d, byte ptr [rdx+5]
0x1400201a6  movzx   edx, byte ptr [rdx+4]
0x1400201aa  call    StRtlIoStorInfoSetSenseCode
0x1400201af  mov     rax, [rsp+78h+arg_28]
0x1400201b7  mov     [rax], edi
0x1400201b9  jmp     loc_1400203A9
0x1400201be  mov     rax, [rsp+78h+arg_28]
0x1400201c6  mov     r9d, edi
0x1400201c9  mov     rdx, [rsp+78h+arg_30]
0x1400201d1  mov     r8d, ebp
0x1400201d4  mov     rcx, rbx
0x1400201d7  mov     [rsp+78h+var_58], rax
0x1400201dc  call    Smb2BufferErrorResponse
0x1400201e1  mov     edi, eax
0x1400201e3  jmp     loc_1400203B0
0x1400201e8  mov     edx, [rbx+58Ch]
0x1400201ee  mov     ecx, edx
0x1400201f0  shl     ecx, 4
0x1400201f3  add     rcx, 40h ; '@'
0x1400201f7  cmp     rcx, rbp
0x1400201fa  jbe     short loc_140020250
0x1400201fc  mov     rcx, [rsp+78h+arg_28]
0x140020204  mov     eax, [rsp+78h+arg_20]
0x14002020b  mov     [rcx], eax
0x14002020d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140020214  lea     rax, WPP_GLOBAL_Control
0x14002021b  cmp     rcx, rax
0x14002021e  jz      short loc_140020245
0x140020220  mov     eax, [rcx+2Ch]
0x140020223  test    al, 1
0x140020225  jz      short loc_140020245
0x140020227  cmp     byte ptr [rcx+29h], 1
0x14002022b  jb      short loc_140020245
0x14002022d  mov     edx, 16h
0x140020232  mov     rcx, [rcx+18h]
0x140020236  lea     r8, WPP_37fe073fcb403a48ea10fb83da93c962_Traceguids
0x14002023d  mov     r9, r14
0x140020240  call    WPP_SF_q
0x140020245  mov     r15d, 0C00000C3h
0x14002024b  jmp     loc_1400203A9
0x140020250  mov     rcx, [rsp+78h+arg_30]
0x140020258  xor     r8d, r8d
0x14002025b  add     rcx, 40h ; '@'
0x14002025f  xor     eax, eax
0x140020261  cmp     eax, edx
0x140020263  jnb     short loc_1400202C8
0x140020265  cmp     word ptr [rcx], 11h
0x140020269  jnz     short loc_140020277
0x14002026b  add     r8d, [rcx+4]
0x14002026f  add     rcx, 10h
0x140020273  inc     eax
0x140020275  jmp     short loc_140020261
0x140020277  mov     rcx, [rsp+78h+arg_28]
0x14002027f  mov     eax, [rsp+78h+arg_20]
0x140020286  mov     [rcx], eax
0x140020288  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002028f  lea     rax, WPP_GLOBAL_Control
0x140020296  cmp     rcx, rax
0x140020299  jz      short loc_140020245
0x14002029b  mov     eax, [rcx+2Ch]
0x14002029e  test    al, 1
0x1400202a0  jz      short loc_140020245
0x1400202a2  cmp     byte ptr [rcx+29h], 1
0x1400202a6  jb      short loc_140020245
0x1400202a8  mov     rcx, [rcx+18h]
0x1400202ac  lea     r8, WPP_37fe073fcb403a48ea10fb83da93c962_Traceguids
0x1400202b3  mov     edx, 17h
0x1400202b8  call    WPP_SF_
0x1400202bd  mov     r15d, 0C00000C3h
0x1400202c3  jmp     loc_1400203A9
0x1400202c8  test    rdi, rdi
0x1400202cb  jnz     loc_14002042E
0x1400202d1  cmp     r8d, [rbx+2E8h]
0x1400202d8  ja      loc_14002043B
0x1400202de  xor     edx, edx
0x1400202e0  mov     [rbx+2ECh], r8d
0x1400202e7  mov     eax, r12d
0x1400202ea  div     r13d
0x1400202ed  lea     rdi, [rdx+rdx*2]
0x1400202f1  shl     rdi, 6
0x1400202f5  add     rdi, [rsp+78h+arg_8]
0x1400202fd  cmp     dword ptr [r14+41Ch], 1
0x140020305  jnz     short loc_14002035D
0x140020307  cmp     byte ptr [r14+420h], 0
0x14002030f  jz      short loc_14002035D
0x140020311  mov     eax, [r14+44h]
0x140020315  test    eax, 1000800h
0x14002031a  jnz     short loc_14002035D
0x14002031c  mov     rax, [r14+48h]
0x140020320  cmp     dword ptr [rax+278h], 1
0x140020327  jbe     short loc_140020354
0x140020329  mov     rcx, [r14+0C8h]
0x140020330  mov     rax, 0E5109EC205D7BEA7h
0x14002033a  mul     rcx
0x14002033d  shr     rdx, 1Dh
0x140020341  imul    rax, rdx, 23C34600h
0x140020348  sub     rcx, rax
0x14002034b  cmp     rcx, 4C4B40h
0x140020352  jb      short loc_14002035D
0x140020354  lock or dword ptr [r14+44h], 100000h
0x14002035d  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140020364  nop     dword ptr [rax+rax+00h]
0x140020369  test    byte ptr [rax+40h], 1
0x14002036d  jz      short loc_140020384
0x14002036f  cmp     qword ptr [rbx+350h], 0
0x140020377  jz      short loc_140020384
0x140020379  mov     rdx, rbx
0x14002037c  mov     rcx, rdi
0x14002037f  call    Smb2Write_UpdatePerfCounters
0x140020384  cmp     byte ptr [rbx+358h], 0
0x14002038b  jz      short loc_140020398
0x14002038d  lock dec dword ptr [rdi+58h]
0x140020391  mov     byte ptr [rbx+358h], 0
0x140020398  mov     rdx, [rsp+78h+arg_28]
0x1400203a0  mov     eax, [rsp+78h+arg_20]
0x1400203a7  mov     [rdx], eax
0x1400203a9  mov     edi, [rsp+78h+arg_0]
0x1400203b0  lea     rcx, [rbx+370h]
0x1400203b7  call    cs:__imp_RDR_PERF_EXIT
0x1400203be  nop     dword ptr [rax+rax+00h]
0x1400203c3  lea     rcx, [rbx+370h]
0x1400203ca  call    cs:__imp_RDR_PERF_OUTPUT_ETW
0x1400203d1  nop     dword ptr [rax+rax+00h]
0x1400203d6  lea     rcx, [rbx+370h]
0x1400203dd  call    cs:__imp_RDR_PERF_FREE
0x1400203e4  nop     dword ptr [rax+rax+00h]
0x1400203e9  mov     dword ptr [rsp+78h+arg_10], r15d
0x1400203f1  mov     rcx, rbx
0x1400203f4  mov     dword ptr [rsp+78h+arg_10+4], 0
0x1400203ff  mov     rdx, [rsp+78h+arg_10]
0x140020407  call    cs:__imp_SmbCseUpdateBufferContextStatus
0x14002040e  nop     dword ptr [rax+rax+00h]
0x140020413  mov     rbx, [rsp+78h+arg_18]
0x14002041b  mov     eax, edi
0x14002041d  add     rsp, 40h
0x140020421  pop     r15
0x140020423  pop     r14
0x140020425  pop     r13
0x140020427  pop     r12
0x140020429  pop     rdi
0x14002042a  pop     rsi
0x14002042b  pop     rbp
0x14002042c  retn
0x14002042e  cmp     r8d, [rbx+308h]
0x140020435  jbe     loc_1400202DE
0x14002043b  mov     rcx, [rsp+78h+arg_28]
0x140020443  mov     eax, [rsp+78h+arg_20]
0x14002044a  mov     [rcx], eax
0x14002044c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140020453  lea     rax, WPP_GLOBAL_Control
0x14002045a  cmp     rcx, rax
0x14002045d  jz      loc_140020245
0x140020463  mov     eax, [rcx+2Ch]
0x140020466  test    al, 1
0x140020468  jz      loc_140020245
0x14002046e  cmp     byte ptr [rcx+29h], 1
0x140020472  jb      loc_140020245
0x140020478  mov     edx, 18h
0x14002047d  jmp     loc_140020232
```
