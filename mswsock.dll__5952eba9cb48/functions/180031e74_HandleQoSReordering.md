# HandleQoSReordering

- ea: `0x180031e74`
- end: `0x18003228d`
- name: `HandleQoSReordering`
- size: `1049`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180032294`

## callees

- `0x180031e74`
- `0x1800327a8`
- `0x1800327f0`
- `0x180038104`
- `0x18003ae8c`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180032135`
- `ntdll!RtlFreeHeap` at `0x18003214d`
- `ntdll!RtlFreeHeap` at `0x18003220f`
- `ntdll!RtlFreeHeap` at `0x18003222c`
- `ntdll!RtlFreeHeap` at `0x180032135`
- `ntdll!RtlFreeHeap` at `0x18003214d`
- `ntdll!RtlFreeHeap` at `0x18003220f`
- `ntdll!RtlFreeHeap` at `0x18003222c`
- `WS2_32!WSCWriteProviderOrderEx` at `0x18003209b`
- `WS2_32!WSCWriteProviderOrderEx` at `0x18003209b`
- `WS2_32!WSCEnumProtocolsEx` at `0x180031ee8`
- `WS2_32!WSCEnumProtocolsEx` at `0x180031f53`
- `WS2_32!WSCEnumProtocolsEx` at `0x180031ee8`
- `WS2_32!WSCEnumProtocolsEx` at `0x180031f53`

## string_xrefs

- `0x1800321f7`: `Failed to enumerate protocols`
- `0x180032187`: `Failed to get number of protocols for reordering`
- `0x1800320b6`: `Failed to write the reordered catalog`

## pseudocode

```c
__int64 __fastcall HandleQoSReordering(__int64 a1, _QWORD *a2, _QWORD *a3, __int64 a4)
{
  __int64 v4; // r12
  int v6; // r15d
  unsigned int v7; // eax
  __int64 v8; // rax
  char *v9; // rdi
  _DWORD *v10; // rbx
  unsigned int v11; // eax
  unsigned int v12; // esi
  int v13; // edx
  int v14; // r10d
  int v15; // r8d
  int v16; // r11d
  _QWORD *v17; // r12
  __int64 v18; // r14
  __int64 v19; // r9
  __int64 v20; // rax
  int v21; // eax
  int v22; // eax
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // rcx
  int i; // r8d
  __int64 v27; // rcx
  __int64 v28; // rcx
  unsigned int v29; // eax
  char v30; // al
  const wchar_t *v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rcx
  const wchar_t *v34; // rdx
  _DWORD v36[18]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v37; // [rsp+80h] [rbp+8h] BYREF
  _QWORD *v38; // [rsp+88h] [rbp+10h]
  __int64 v39; // [rsp+98h] [rbp+20h]

  v39 = a4;
  v38 = a2;
  v37 = a1;
  v4 = a4;
  v36[0] = 0;
  v6 = 3;
  while ( 1 )
  {
    LODWORD(v37) = 0;
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_(1025, 40, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids);
    v36[0] = 0;
    if ( (unsigned int)WSCEnumProtocolsEx(0, 0, v36, &v37, v4) == -1 )
    {
      v7 = v37;
      if ( (_DWORD)v37 != 10055 )
      {
        if ( (xmmword_180063D60 & 2) != 0 )
        {
          WPP_SF_d(1025, 41, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids, (unsigned int)v37);
          v7 = v37;
        }
        v31 = L"Failed to get number of protocols for reordering";
        v32 = v7;
        goto LABEL_54;
      }
    }
    v8 = ((__int64 (__fastcall *)(HANDLE, _QWORD, _QWORD))SockAllocateHeapRoutine)(SockPrivateHeap, 0, v36[0]);
    v9 = (char *)v8;
    if ( !v8 )
    {
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_(1025, 42, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids);
      LODWORD(v37) = 10055;
      v31 = L"Failed to allocate space for rgProts for reordering";
      v32 = 10055;
LABEL_54:
      LogError(v32, v31);
      return (unsigned int)v37;
    }
    LODWORD(v37) = 0;
    v10 = 0;
    v11 = WSCEnumProtocolsEx(0, v8, v36, &v37, v4);
    v12 = v11;
    if ( v11 == -1 )
    {
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_d(1025, 43, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids, (unsigned int)v37);
      v33 = (unsigned int)v37;
      v34 = L"Failed to enumerate protocols";
      goto LABEL_48;
    }
    v10 = (_DWORD *)((__int64 (__fastcall *)(HANDLE, _QWORD, __int64))SockAllocateHeapRoutine)(
                      SockPrivateHeap,
                      0,
                      4LL * (int)v11);
    if ( !v10 )
      break;
    v13 = v12 - 1;
    v14 = -1;
    v15 = 0;
    v16 = v12 - 1;
    if ( (int)(v12 - 1) < 0 )
      goto LABEL_49;
    v17 = v38;
    v18 = v13;
    do
    {
      v19 = 628 * v18;
      v20 = *(_QWORD *)&v9[628 * v18 + 20] - *v17;
      if ( !v20 )
        v20 = *(_QWORD *)&v9[v19 + 28] - v17[1];
      if ( !v20 )
      {
        v21 = v13;
        if ( v14 != -1 )
          v21 = v14;
        v14 = v21;
        v22 = *(_DWORD *)&v9[v19 + 36];
        goto LABEL_27;
      }
      v23 = *(_QWORD *)&v9[v19 + 20] - *a3;
      if ( !v23 )
        v23 = *(_QWORD *)&v9[v19 + 28] - a3[1];
      if ( v23 )
      {
        v22 = *(_DWORD *)&v9[v19 + 36];
LABEL_27:
        v28 = v13--;
        v10[v28] = v22;
        goto LABEL_28;
      }
      if ( v14 == -1 )
      {
        v24 = *(_DWORD *)&v9[v19 + 36];
        v25 = v13;
      }
      else
      {
        for ( i = v13; i < v14; v10[v27] = v10[v27 + 1] )
          v27 = i++;
        v24 = *(_DWORD *)&v9[v19 + 36];
        --v14;
        v25 = i;
        v15 = 1;
      }
      v10[v25] = v24;
      --v13;
LABEL_28:
      --v16;
      --v18;
    }
    while ( v16 >= 0 );
    v4 = v39;
    if ( !v15 )
      goto LABEL_49;
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_(1025, 45, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids);
    v29 = WSCWriteProviderOrderEx(v10, v12, v4);
    LODWORD(v37) = v29;
    if ( !v29 )
      goto LABEL_49;
    LogError(v29, L"Failed to write the reordered catalog");
    v30 = xmmword_180063D60;
    if ( (xmmword_180063D60 & 2) != 0 )
    {
      WPP_SF_d(1025, 46, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids, (unsigned int)v37);
      v30 = xmmword_180063D60;
    }
    if ( !v6 )
      goto LABEL_49;
    --v6;
    if ( (v30 & 2) != 0 )
      WPP_SF_(1025, 47, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids);
    LogMsg(L"Retrying reodering the catalog");
    RtlFreeHeap(SockPrivateHeap, 0, v9);
    RtlFreeHeap(SockPrivateHeap, 0, v10);
  }
  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_(1025, 44, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids);
  v33 = 10055;
  v34 = L"Failed to allocate space for rgCids for reordering";
  LODWORD(v37) = 10055;
LABEL_48:
  LogError(v33, v34);
LABEL_49:
  RtlFreeHeap(SockPrivateHeap, 0, v9);
  if ( v10 )
    RtlFreeHeap(SockPrivateHeap, 0, v10);
  return (unsigned int)v37;
}

```

## disassembly

```asm
0x180031e74  mov     rax, rsp
0x180031e77  mov     [rax+20h], r9
0x180031e7b  mov     [rax+10h], rdx
0x180031e7f  mov     [rax+8], rcx
0x180031e83  push    rbx
0x180031e84  push    rsi
0x180031e85  push    rdi
0x180031e86  push    r12
0x180031e88  push    r13
0x180031e8a  push    r14
0x180031e8c  push    r15
0x180031e8e  sub     rsp, 40h
0x180031e92  xor     r14d, r14d
0x180031e95  mov     r12, r9
0x180031e98  mov     r13, r8
0x180031e9b  mov     [rax-48h], r14d
0x180031e9f  mov     sil, 2
0x180031ea2  lea     r15d, [r14+3]
0x180031ea6  mov     dword ptr [rsp+78h+arg_0], r14d
0x180031eae  test    byte ptr cs:xmmword_180063D60, sil
0x180031eb5  jz      short loc_180031ECD
0x180031eb7  mov     edx, 28h ; '('
0x180031ebc  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x180031ec3  mov     ecx, 401h
0x180031ec8  call    WPP_SF_
0x180031ecd  lea     r9, [rsp+78h+arg_0]
0x180031ed5  mov     [rsp+78h+var_48], r14d
0x180031eda  lea     r8, [rsp+78h+var_48]
0x180031edf  mov     [rsp+78h+var_58], r12
0x180031ee4  xor     edx, edx
0x180031ee6  xor     ecx, ecx
0x180031ee8  call    cs:__imp_WSCEnumProtocolsEx
0x180031eef  nop     dword ptr [rax+rax+00h]
0x180031ef4  cmp     eax, 0FFFFFFFFh
0x180031ef7  jnz     short loc_180031F0B
0x180031ef9  mov     eax, dword ptr [rsp+78h+arg_0]
0x180031f00  cmp     eax, 2747h
0x180031f05  jnz     loc_18003215E
0x180031f0b  mov     r8d, [rsp+78h+var_48]
0x180031f10  xor     edx, edx
0x180031f12  mov     rcx, cs:SockPrivateHeap
0x180031f19  mov     rax, cs:SockAllocateHeapRoutine
0x180031f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f25  mov     rdi, rax
0x180031f28  test    rax, rax
0x180031f2b  jz      loc_18003223A
0x180031f31  lea     r9, [rsp+78h+arg_0]
0x180031f39  mov     dword ptr [rsp+78h+arg_0], r14d
0x180031f41  lea     r8, [rsp+78h+var_48]
0x180031f46  mov     [rsp+78h+var_58], r12
0x180031f4b  mov     rdx, rax
0x180031f4e  xor     ecx, ecx
0x180031f50  mov     rbx, r14
0x180031f53  call    cs:__imp_WSCEnumProtocolsEx
0x180031f5a  nop     dword ptr [rax+rax+00h]
0x180031f5f  movsxd  rsi, eax
0x180031f62  cmp     esi, 0FFFFFFFFh
0x180031f65  jz      loc_1800321C9
0x180031f6b  mov     rcx, cs:SockPrivateHeap
0x180031f72  mov     r8, rsi
0x180031f75  mov     rax, cs:SockAllocateHeapRoutine
0x180031f7c  xor     edx, edx
0x180031f7e  shl     r8, 2
0x180031f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f87  mov     rbx, rax
0x180031f8a  test    rax, rax
0x180031f8d  jz      loc_180032195
0x180031f93  lea     edx, [rsi-1]
0x180031f96  or      r10d, 0FFFFFFFFh
0x180031f9a  mov     r8d, r14d
0x180031f9d  mov     r11d, edx
0x180031fa0  test    edx, edx
0x180031fa2  js      loc_180032203
0x180031fa8  mov     r12, [rsp+78h+arg_8]
0x180031fb0  movsxd  r14, edx
0x180031fb3  imul    r9, r14, 274h
0x180031fba  mov     rax, [r9+rdi+14h]
0x180031fbf  sub     rax, [r12]
0x180031fc3  jnz     short loc_180031FCF
0x180031fc5  mov     rax, [r9+rdi+1Ch]
0x180031fca  sub     rax, [r12+8]
0x180031fcf  test    rax, rax
0x180031fd2  jnz     short loc_180031FE8
0x180031fd4  cmp     r10d, 0FFFFFFFFh
0x180031fd8  mov     eax, edx
0x180031fda  cmovnz  eax, r10d
0x180031fde  mov     r10d, eax
0x180031fe1  mov     eax, [r9+rdi+24h]
0x180031fe6  jmp     short loc_18003204B
0x180031fe8  mov     rax, [r9+rdi+14h]
0x180031fed  sub     rax, [r13+0]
0x180031ff1  jnz     short loc_180031FFC
0x180031ff3  mov     rax, [r9+rdi+1Ch]
0x180031ff8  sub     rax, [r13+8]
0x180031ffc  test    rax, rax
0x180031fff  jnz     short loc_180032046
0x180032001  cmp     r10d, 0FFFFFFFFh
0x180032005  jnz     short loc_180032011
0x180032007  mov     eax, [r9+rdi+24h]
0x18003200c  movsxd  rcx, edx
0x18003200f  jmp     short loc_18003203C
0x180032011  mov     r8d, edx
0x180032014  cmp     edx, r10d
0x180032017  jge     short loc_18003202B
0x180032019  movsxd  rcx, r8d
0x18003201c  inc     r8d
0x18003201f  mov     eax, [rbx+rcx*4+4]
0x180032023  mov     [rbx+rcx*4], eax
0x180032026  cmp     r8d, r10d
0x180032029  jl      short loc_180032019
0x18003202b  mov     eax, [rdi+r9+24h]
0x180032030  dec     r10d
0x180032033  movsxd  rcx, r8d
0x180032036  mov     r8d, 1
0x18003203c  mov     [rbx+rcx*4], eax
0x18003203f  or      eax, 0FFFFFFFFh
0x180032042  add     edx, eax
0x180032044  jmp     short loc_180032053
0x180032046  mov     eax, [rdi+r9+24h]
0x18003204b  movsxd  rcx, edx
0x18003204e  dec     edx
0x180032050  mov     [rbx+rcx*4], eax
0x180032053  sub     r11d, 1
0x180032057  lea     r14, [r14-1]
0x18003205b  jns     loc_180031FB3
0x180032061  mov     r12, [rsp+78h+arg_18]
0x180032069  xor     r14d, r14d
0x18003206c  test    r8d, r8d
0x18003206f  jz      loc_180032203
0x180032075  test    byte ptr cs:xmmword_180063D60, 2
0x18003207c  jz      short loc_180032093
0x18003207e  lea     edx, [r14+2Dh]
0x180032082  mov     ecx, 401h
0x180032087  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x18003208e  call    WPP_SF_
0x180032093  mov     r8, r12
0x180032096  mov     edx, esi
0x180032098  mov     rcx, rbx
0x18003209b  call    cs:__imp_WSCWriteProviderOrderEx
0x1800320a2  nop     dword ptr [rax+rax+00h]
0x1800320a7  mov     dword ptr [rsp+78h+arg_0], eax
0x1800320ae  test    eax, eax
0x1800320b0  jz      loc_180032203
0x1800320b6  lea     rdx, aFailedToWriteT; "Failed to write the reordered catalog"
0x1800320bd  mov     ecx, eax
0x1800320bf  call    LogError
0x1800320c4  mov     al, byte ptr cs:xmmword_180063D60
0x1800320ca  mov     sil, 2
0x1800320cd  test    sil, al
0x1800320d0  jz      short loc_1800320F6
0x1800320d2  mov     r9d, dword ptr [rsp+78h+arg_0]
0x1800320da  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x1800320e1  mov     edx, 2Eh ; '.'
0x1800320e6  mov     ecx, 401h
0x1800320eb  call    WPP_SF_d
0x1800320f0  mov     al, byte ptr cs:xmmword_180063D60
0x1800320f6  test    r15d, r15d
0x1800320f9  jz      loc_180032203
0x1800320ff  dec     r15d
0x180032102  test    sil, al
0x180032105  jz      short loc_18003211D
0x180032107  mov     edx, 2Fh ; '/'
0x18003210c  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x180032113  mov     ecx, 401h
0x180032118  call    WPP_SF_
0x18003211d  lea     rcx, aRetryingReoder; "Retrying reodering the catalog"
0x180032124  call    LogMsg
0x180032129  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180032130  mov     r8, rdi; P
0x180032133  xor     edx, edx; Flags
0x180032135  call    cs:__imp_RtlFreeHeap
0x18003213c  nop     dword ptr [rax+rax+00h]
0x180032141  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180032148  mov     r8, rbx; P
0x18003214b  xor     edx, edx; Flags
0x18003214d  call    cs:__imp_RtlFreeHeap
0x180032154  nop     dword ptr [rax+rax+00h]
0x180032159  jmp     loc_180031EA6
0x18003215e  test    byte ptr cs:xmmword_180063D60, sil
0x180032165  jz      short loc_180032187
0x180032167  mov     edx, 29h ; ')'
0x18003216c  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x180032173  mov     ecx, 401h
0x180032178  mov     r9d, eax
0x18003217b  call    WPP_SF_d
0x180032180  mov     eax, dword ptr [rsp+78h+arg_0]
0x180032187  lea     rdx, aFailedToGetNum; "Failed to get number of protocols for r"...
0x18003218e  mov     ecx, eax
0x180032190  jmp     loc_180032270
0x180032195  test    byte ptr cs:xmmword_180063D60, 2
0x18003219c  jz      short loc_1800321B4
0x18003219e  mov     edx, 2Ch ; ','
0x1800321a3  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x1800321aa  mov     ecx, 401h
0x1800321af  call    WPP_SF_
0x1800321b4  mov     ecx, 2747h
0x1800321b9  lea     rdx, aFailedToAlloca; "Failed to allocate space for rgCids for"...
0x1800321c0  mov     dword ptr [rsp+78h+arg_0], ecx
0x1800321c7  jmp     short loc_1800321FE
0x1800321c9  test    byte ptr cs:xmmword_180063D60, 2
0x1800321d0  jz      short loc_1800321F0
0x1800321d2  mov     r9d, dword ptr [rsp+78h+arg_0]
0x1800321da  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x1800321e1  mov     edx, 2Bh ; '+'
0x1800321e6  mov     ecx, 401h
0x1800321eb  call    WPP_SF_d
0x1800321f0  mov     ecx, dword ptr [rsp+78h+arg_0]
0x1800321f7  lea     rdx, aFailedToEnumer; "Failed to enumerate protocols"
0x1800321fe  call    LogError
0x180032203  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18003220a  mov     r8, rdi; P
0x18003220d  xor     edx, edx; Flags
0x18003220f  call    cs:__imp_RtlFreeHeap
0x180032216  nop     dword ptr [rax+rax+00h]
0x18003221b  test    rbx, rbx
0x18003221e  jz      short loc_180032275
0x180032220  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180032227  mov     r8, rbx; P
0x18003222a  xor     edx, edx; Flags
0x18003222c  call    cs:__imp_RtlFreeHeap
0x180032233  nop     dword ptr [rax+rax+00h]
0x180032238  jmp     short loc_180032275
0x18003223a  test    byte ptr cs:xmmword_180063D60, sil
0x180032241  jz      short loc_180032259
0x180032243  mov     edx, 2Ah ; '*'
0x180032248  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x18003224f  mov     ecx, 401h
0x180032254  call    WPP_SF_
0x180032259  mov     dword ptr [rsp+78h+arg_0], 2747h
0x180032264  lea     rdx, aFailedToAlloca_3; "Failed to allocate space for rgProts fo"...
0x18003226b  mov     ecx, 2747h
0x180032270  call    LogError
0x180032275  mov     eax, dword ptr [rsp+78h+arg_0]
0x18003227c  add     rsp, 40h
0x180032280  pop     r15
0x180032282  pop     r14
0x180032284  pop     r13
0x180032286  pop     r12
0x180032288  pop     rdi
0x180032289  pop     rsi
0x18003228a  pop     rbx
0x18003228b  retn
```
