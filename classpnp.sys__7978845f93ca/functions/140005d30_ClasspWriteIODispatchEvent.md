# ClasspWriteIODispatchEvent

- ea: `0x140005d30`
- end: `0x1400061d1`
- name: `ClasspWriteIODispatchEvent`
- size: `1185`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x140004950`

## callees

- `0x140005d30`
- `0x1400061e0`

## import_xrefs

- `ntoskrnl!IoGetGenericIrpExtension` at `0x140005eaa`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x140005eaa`

## pseudocode

```c
char __fastcall ClasspWriteIODispatchEvent(__int64 a1)
{
  __int64 v1; // r9
  char *v3; // rax
  char v4; // al
  bool v5; // cf
  __int64 v6; // r8
  char v7; // r11
  char *v8; // r10
  unsigned int v9; // ebp
  unsigned int i; // r14d
  __int64 v11; // rcx
  unsigned __int64 v12; // rdi
  __int64 v13; // r15
  __int64 v14; // rsi
  int v15; // ecx
  char v16; // di
  __int64 v17; // rbp
  char v18; // r11
  char v19; // dl
  char v20; // cl
  char v21; // dl
  int v22; // esi
  __int64 v23; // rdx
  int v24; // ecx
  __int64 v25; // rdx
  int v26; // ecx
  unsigned int v27; // esi
  unsigned int v28; // r15d
  __int64 v29; // rdx
  unsigned __int64 v30; // r14
  __int64 v31; // r13
  __int64 v32; // r12
  int v33; // edx
  unsigned __int64 v34; // rdx
  int v35; // ecx
  int v36; // edx
  int v38; // [rsp+90h] [rbp+8h] BYREF
  __int64 v39; // [rsp+98h] [rbp+10h]

  v1 = *(_QWORD *)(a1 + 48);
  v39 = 0;
  v38 = 0;
  v3 = *(char **)(v1 + 184);
  if ( !v3 )
    return (char)v3;
  v4 = *v3;
  v5 = v4 == 3;
  LOBYTE(v3) = v4 - 3;
  if ( !v5 && (_BYTE)v3 != 1 )
    return (char)v3;
  v6 = *(_QWORD *)(a1 + 288);
  v7 = *(_BYTE *)(v6 + 2);
  if ( v7 != 40 )
  {
    v8 = (char *)(v6 + 72);
    goto LABEL_12;
  }
  v8 = 0;
  if ( !*(_DWORD *)(v6 + 20) )
  {
    v9 = *(_DWORD *)(v6 + 56);
    if ( v9 )
    {
      for ( i = 0; i < v9; ++i )
      {
        LOBYTE(v3) = i;
        v11 = *(unsigned int *)(v6 + 4LL * i + 120);
        if ( (unsigned int)v11 >= 0x80 )
        {
          v12 = *(unsigned int *)(v6 + 16);
          if ( (unsigned int)v11 < (unsigned int)v12 )
          {
            v13 = v11 + v6;
            v14 = (unsigned int)v11;
            v15 = *(_DWORD *)(v11 + v6);
            if ( v15 == 64 )
            {
              if ( v14 + 40 <= v12 )
              {
                if ( *(_BYTE *)(v13 + 10) )
                  v8 = (char *)(v13 + 24);
                break;
              }
            }
            else
            {
              v35 = v15 - 65;
              if ( v35 )
              {
                if ( v35 == 1 && v14 + 40 <= v12 )
                {
                  if ( *(_DWORD *)(v13 + 12) )
                    v8 = (char *)(v13 + 32);
                  break;
                }
              }
              else if ( v14 + 56 <= v12 )
              {
                if ( *(_BYTE *)(v13 + 10) )
                  v8 = (char *)(v13 + 24);
                break;
              }
            }
          }
        }
      }
    }
  }
LABEL_12:
  if ( !v8 )
    return (char)v3;
  v16 = *v8;
  v17 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 64LL);
  LOBYTE(v3) = -1;
  if ( v7 != 40 )
  {
    v18 = *(_BYTE *)(v6 + 10);
    goto LABEL_15;
  }
  v18 = 0;
  if ( *(_DWORD *)(v6 + 20) )
    goto LABEL_15;
  v27 = *(_DWORD *)(v6 + 56);
  if ( !v27 )
    goto LABEL_15;
  v28 = 0;
  while ( 1 )
  {
    v29 = *(unsigned int *)(v6 + 4LL * v28 + 120);
    if ( (unsigned int)v29 < 0x80 )
      goto LABEL_38;
    v30 = *(unsigned int *)(v6 + 16);
    if ( (unsigned int)v29 >= (unsigned int)v30 )
      goto LABEL_38;
    v31 = v29 + v6;
    v32 = (unsigned int)v29;
    v33 = *(_DWORD *)(v29 + v6);
    if ( v33 == 64 )
    {
      v34 = v32 + 40;
      goto LABEL_37;
    }
    v36 = v33 - 65;
    if ( !v36 )
      break;
    if ( v36 == 1 && v32 + 40 <= v30 )
      goto LABEL_15;
LABEL_38:
    if ( ++v28 >= v27 )
      goto LABEL_15;
  }
  v34 = v32 + 56;
LABEL_37:
  if ( v34 > v30 )
    goto LABEL_38;
  v18 = *(_BYTE *)(v31 + 10);
LABEL_15:
  if ( v18 == 16 )
  {
    HIBYTE(v39) = v8[2];
    BYTE6(v39) = v8[3];
    BYTE5(v39) = v8[4];
    BYTE4(v39) = v8[5];
    BYTE3(v39) = v8[6];
    BYTE2(v39) = v8[7];
    BYTE1(v39) = v8[8];
    LOBYTE(v39) = v8[9];
    HIBYTE(v38) = v8[10];
    BYTE2(v38) = v8[11];
    BYTE1(v38) = v8[12];
    LOBYTE(v38) = v8[13];
  }
  else
  {
    v19 = v8[7];
    BYTE3(v39) = v8[2];
    BYTE2(v39) = v8[3];
    BYTE1(v39) = v8[4];
    v20 = v8[5];
    BYTE1(v38) = v19;
    v21 = v8[8];
    LOBYTE(v39) = v20;
    LOBYTE(v38) = v21;
  }
  v22 = *(_DWORD *)(v17 + 572) * v38;
  if ( v1 )
  {
    v38 = 0;
    if ( (int)IoGetGenericIrpExtension(v1, &v38, 4) >= 0 && (v38 & 0x10) != 0 )
      LOBYTE(v3) = v38 & 0xF;
    else
      LOBYTE(v3) = -1;
  }
  if ( ((v16 - 8) & 0x5F) != 0 )
  {
    if ( ((v16 - 10) & 0x5F) == 0 )
    {
      v25 = *(_QWORD *)(a1 + 48);
      v26 = *(_DWORD *)(v25 + 16);
      if ( (v26 & 0x42) != 0 )
      {
        if ( (BYTE1(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 8) != 0 )
          LOBYTE(v3) = McTemplateK0qpuxipu_EtwWriteTransfer(
                         v26,
                         (unsigned int)EventPagingWriteRequest,
                         (int)a1 + 328,
                         *(_DWORD *)(v17 + 588),
                         *(_QWORD *)(a1 + 32),
                         v16,
                         v22,
                         v39,
                         v25,
                         (char)v3);
      }
      else if ( *(_BYTE *)(a1 + 209) )
      {
        if ( (BYTE1(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x20) != 0 )
          LOBYTE(v3) = McTemplateK0qpuxipu_EtwWriteTransfer(
                         v26,
                         (unsigned int)EventLowMemoryWriteRequest,
                         (int)a1 + 328,
                         *(_DWORD *)(v17 + 588),
                         *(_QWORD *)(a1 + 32),
                         v16,
                         v22,
                         v39,
                         v25,
                         (char)v3);
      }
      else if ( (BYTE1(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 2) != 0 )
      {
        LOBYTE(v3) = McTemplateK0qpuxipu_EtwWriteTransfer(
                       v26,
                       (unsigned int)EventWriteRequest,
                       (int)a1 + 328,
                       *(_DWORD *)(v17 + 588),
                       *(_QWORD *)(a1 + 32),
                       v16,
                       v22,
                       v39,
                       v25,
                       (char)v3);
      }
    }
  }
  else
  {
    v23 = *(_QWORD *)(a1 + 48);
    v24 = *(_DWORD *)(v23 + 16);
    if ( (v24 & 0x42) != 0 )
    {
      if ( (BYTE1(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 4) != 0 )
        LOBYTE(v3) = McTemplateK0qpuxipu_EtwWriteTransfer(
                       v24,
                       (unsigned int)EventPagingReadRequest,
                       (int)a1 + 328,
                       *(_DWORD *)(v17 + 588),
                       *(_QWORD *)(a1 + 32),
                       v16,
                       v22,
                       v39,
                       v23,
                       (char)v3);
    }
    else if ( *(_BYTE *)(a1 + 209) )
    {
      if ( (BYTE1(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x10) != 0 )
        LOBYTE(v3) = McTemplateK0qpuxipu_EtwWriteTransfer(
                       v24,
                       (unsigned int)EventLowMemoryReadRequest,
                       (int)a1 + 328,
                       *(_DWORD *)(v17 + 588),
                       *(_QWORD *)(a1 + 32),
                       v16,
                       v22,
                       v39,
                       v23,
                       (char)v3);
    }
    else if ( (BYTE1(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 1) != 0 )
    {
      LOBYTE(v3) = McTemplateK0qpuxipu_EtwWriteTransfer(
                     v24,
                     (unsigned int)EventReadRequest,
                     (int)a1 + 328,
                     *(_DWORD *)(v17 + 588),
                     *(_QWORD *)(a1 + 32),
                     v16,
                     v22,
                     v39,
                     v23,
                     (char)v3);
    }
  }
  return (char)v3;
}

```

## disassembly

```asm
0x140005d30  mov     r11, rsp
0x140005d33  push    rbx
0x140005d34  sub     rsp, 80h
0x140005d3b  mov     r9, [rcx+30h]
0x140005d3f  mov     rbx, rcx
0x140005d42  xor     ecx, ecx
0x140005d44  mov     [rsp+88h+arg_8], rcx
0x140005d4c  mov     [rsp+88h+arg_0], ecx
0x140005d53  mov     rax, [r9+0B8h]
0x140005d5a  test    rax, rax
0x140005d5d  jz      loc_140005F44
0x140005d63  movzx   eax, byte ptr [rax]
0x140005d66  sub     al, 3
0x140005d68  cmp     al, 1
0x140005d6a  ja      loc_140005F44
0x140005d70  mov     r8, [rbx+120h]
0x140005d77  mov     [r11+18h], rbp
0x140005d7b  mov     [r11-10h], rsi
0x140005d7f  mov     [r11-18h], rdi
0x140005d83  mov     [r11-30h], r14
0x140005d87  mov     [r11-38h], r15
0x140005d8b  movzx   r11d, byte ptr [r8+2]
0x140005d90  cmp     r11b, 28h ; '('
0x140005d94  jnz     loc_140005F4E
0x140005d9a  mov     r10d, ecx
0x140005d9d  cmp     [r8+14h], ecx
0x140005da1  jnz     short loc_140005DEF
0x140005da3  mov     ebp, [r8+38h]
0x140005da7  test    ebp, ebp
0x140005da9  jz      short loc_140005DEF
0x140005dab  mov     r14d, ecx
0x140005dae  mov     eax, r14d
0x140005db1  mov     ecx, [r8+rax*4+78h]
0x140005db6  cmp     ecx, 80h
0x140005dbc  jb      short loc_140005DE5
0x140005dbe  mov     edi, [r8+10h]
0x140005dc2  cmp     ecx, edi
0x140005dc4  jnb     short loc_140005DE5
0x140005dc6  lea     r15, [rcx+r8]
0x140005dca  mov     esi, ecx
0x140005dcc  mov     ecx, [r15]
0x140005dcf  cmp     ecx, 40h ; '@'
0x140005dd2  jnz     loc_140005FEF
0x140005dd8  lea     rcx, [rsi+28h]
0x140005ddc  cmp     rcx, rdi
0x140005ddf  jbe     loc_140006085
0x140005de5  inc     r14d
0x140005de8  cmp     r14d, ebp
0x140005deb  jb      short loc_140005DAE
0x140005ded  xor     ecx, ecx
0x140005def  test    r10, r10
0x140005df2  jz      loc_140005F28
0x140005df8  mov     rax, [rbx+28h]
0x140005dfc  movzx   edi, byte ptr [r10]
0x140005e00  mov     [rsp+88h+var_20], r12
0x140005e05  mov     [rsp+88h+var_28], r13
0x140005e0a  mov     rbp, [rax+40h]
0x140005e0e  mov     al, 0FFh
0x140005e10  cmp     r11b, 28h ; '('
0x140005e14  jz      loc_140005F8D
0x140005e1a  movzx   r11d, byte ptr [r8+0Ah]
0x140005e1f  mov     r13, [rsp+88h+var_28]
0x140005e24  mov     r12, [rsp+88h+var_20]
0x140005e29  movzx   ecx, byte ptr [r10+2]
0x140005e2e  cmp     r11b, 10h
0x140005e32  jz      loc_1400060D1
0x140005e38  movzx   edx, byte ptr [r10+7]
0x140005e3d  mov     byte ptr [rsp+88h+arg_8+3], cl
0x140005e44  movzx   ecx, byte ptr [r10+3]
0x140005e49  mov     byte ptr [rsp+88h+arg_8+2], cl
0x140005e50  movzx   ecx, byte ptr [r10+4]
0x140005e55  mov     byte ptr [rsp+88h+arg_8+1], cl
0x140005e5c  movzx   ecx, byte ptr [r10+5]
0x140005e61  mov     byte ptr [rsp+88h+arg_0+1], dl
0x140005e68  movzx   edx, byte ptr [r10+8]
0x140005e6d  mov     byte ptr [rsp+88h+arg_8], cl
0x140005e74  mov     byte ptr [rsp+88h+arg_0], dl
0x140005e7b  mov     esi, [rsp+88h+arg_0]
0x140005e82  imul    esi, [rbp+23Ch]
0x140005e89  test    r9, r9
0x140005e8c  jz      short loc_140005EC0
0x140005e8e  mov     r8d, 4
0x140005e94  mov     [rsp+88h+arg_0], 0
0x140005e9f  lea     rdx, [rsp+88h+arg_0]
0x140005ea7  mov     rcx, r9
0x140005eaa  call    cs:__imp_IoGetGenericIrpExtension
0x140005eb1  nop     dword ptr [rax+rax+00h]
0x140005eb6  test    eax, eax
0x140005eb8  jns     loc_14000606F
0x140005ebe  mov     al, 0FFh
0x140005ec0  lea     ecx, [rdi-8]
0x140005ec3  test    cl, 5Fh
0x140005ec6  jnz     loc_140005F57
0x140005ecc  mov     rdx, [rbx+30h]
0x140005ed0  mov     ecx, [rdx+10h]
0x140005ed3  test    cl, 42h
0x140005ed6  jz      loc_1400060A2
0x140005edc  test    byte ptr cs:WPP_MAIN_CB.Queue+39h, 4
0x140005ee3  jz      short loc_140005F28
0x140005ee5  mov     [rsp+88h+var_40], al
0x140005ee9  mov     [rsp+88h+var_48], rdx
0x140005eee  lea     rdx, EventPagingReadRequest
0x140005ef5  mov     rax, [rsp+88h+arg_8]
0x140005efd  lea     r8, [rbx+148h]
0x140005f04  mov     r9d, [rbp+24Ch]
0x140005f0b  mov     [rsp+88h+var_50], rax
0x140005f10  mov     rax, [rbx+20h]
0x140005f14  mov     [rsp+88h+var_58], rsi
0x140005f19  mov     [rsp+88h+var_60], dil
0x140005f1e  mov     [rsp+88h+var_68], rax
0x140005f23  call    McTemplateK0qpuxipu_EtwWriteTransfer
0x140005f28  mov     r14, [rsp+88h+var_30]
0x140005f2d  mov     rdi, [rsp+88h+var_18]
0x140005f32  mov     rsi, [rsp+88h+var_10]
0x140005f37  mov     rbp, [rsp+88h+arg_10]
0x140005f3f  mov     r15, [rsp+88h+var_38]
0x140005f44  add     rsp, 80h
0x140005f4b  pop     rbx
0x140005f4c  retn
0x140005f4e  lea     r10, [r8+48h]
0x140005f52  jmp     loc_140005DEF
0x140005f57  lea     ecx, [rdi-0Ah]
0x140005f5a  test    cl, 5Fh
0x140005f5d  jnz     short loc_140005F28
0x140005f5f  mov     rdx, [rbx+30h]
0x140005f63  mov     ecx, [rdx+10h]
0x140005f66  test    cl, 42h
0x140005f69  jz      loc_140006040
0x140005f6f  test    byte ptr cs:WPP_MAIN_CB.Queue+39h, 8
0x140005f76  jz      short loc_140005F28
0x140005f78  mov     [rsp+88h+var_40], al
0x140005f7c  mov     [rsp+88h+var_48], rdx
0x140005f81  lea     rdx, EventPagingWriteRequest
0x140005f88  jmp     loc_140005EF5
0x140005f8d  xor     r11b, r11b
0x140005f90  cmp     dword ptr [r8+14h], 0
0x140005f95  jnz     loc_140005E1F
0x140005f9b  mov     esi, [r8+38h]
0x140005f9f  test    esi, esi
0x140005fa1  jz      loc_140005E1F
0x140005fa7  mov     r15d, ecx
0x140005faa  mov     ecx, r15d
0x140005fad  mov     edx, [r8+rcx*4+78h]
0x140005fb2  cmp     edx, 80h
0x140005fb8  jb      short loc_140005FE1
0x140005fba  mov     r14d, [r8+10h]
0x140005fbe  cmp     edx, r14d
0x140005fc1  jnb     short loc_140005FE1
0x140005fc3  lea     r13, [rdx+r8]
0x140005fc7  mov     r12d, edx
0x140005fca  mov     edx, [r13+0]
0x140005fce  cmp     edx, 40h ; '@'
0x140005fd1  jnz     short loc_140006023
0x140005fd3  lea     rdx, [r12+28h]
0x140005fd8  cmp     rdx, r14
0x140005fdb  jbe     loc_140006098
0x140005fe1  inc     r15d
0x140005fe4  cmp     r15d, esi
0x140005fe7  jnb     loc_140005E1F
0x140005fed  jmp     short loc_140005FAA
0x140005fef  sub     ecx, 41h ; 'A'
0x140005ff2  jz      loc_140006161
0x140005ff8  cmp     ecx, 1
0x140005ffb  jnz     loc_140005DE5
0x140006001  lea     rcx, [rsi+28h]
0x140006005  cmp     rcx, rdi
0x140006008  ja      loc_140005DE5
0x14000600e  xor     ecx, ecx
0x140006010  cmp     [r15+0Ch], r10d
0x140006014  jbe     loc_140005DEF
0x14000601a  lea     r10, [r15+20h]
0x14000601e  jmp     loc_140005DEF
0x140006023  sub     edx, 41h ; 'A'
0x140006026  jz      loc_140006183
0x14000602c  cmp     edx, 1
0x14000602f  jnz     short loc_140005FE1
0x140006031  lea     rdx, [r12+28h]
0x140006036  cmp     rdx, r14
0x140006039  ja      short loc_140005FE1
0x14000603b  jmp     loc_140005E1F
0x140006040  cmp     byte ptr [rbx+0D1h], 0
0x140006047  jnz     loc_14000618D
0x14000604d  test    byte ptr cs:WPP_MAIN_CB.Queue+39h, 2
0x140006054  jz      loc_140005F28
0x14000605a  mov     [rsp+88h+var_40], al
0x14000605e  mov     [rsp+88h+var_48], rdx
0x140006063  lea     rdx, EventWriteRequest
0x14000606a  jmp     loc_140005EF5
0x14000606f  mov     eax, [rsp+88h+arg_0]
0x140006076  test    al, 10h
0x140006078  jz      loc_140005EBE
0x14000607e  and     al, 0Fh
0x140006080  jmp     loc_140005EC0
0x140006085  cmp     [r15+0Ah], r10b
0x140006089  jbe     loc_140005DED
0x14000608f  lea     r10, [r15+18h]
0x140006093  jmp     loc_140005DED
0x140006098  movzx   r11d, byte ptr [r13+0Ah]
0x14000609d  jmp     loc_140005E1F
0x1400060a2  cmp     byte ptr [rbx+0D1h], 0
0x1400060a9  jnz     loc_1400061AF
0x1400060af  test    byte ptr cs:WPP_MAIN_CB.Queue+39h, 1
0x1400060b6  jz      loc_140005F28
0x1400060bc  mov     [rsp+88h+var_40], al
0x1400060c0  mov     [rsp+88h+var_48], rdx
0x1400060c5  lea     rdx, EventReadRequest
0x1400060cc  jmp     loc_140005EF5
0x1400060d1  mov     byte ptr [rsp+88h+arg_8+7], cl
0x1400060d8  movzx   ecx, byte ptr [r10+3]
0x1400060dd  mov     byte ptr [rsp+88h+arg_8+6], cl
0x1400060e4  movzx   ecx, byte ptr [r10+4]
0x1400060e9  mov     byte ptr [rsp+88h+arg_8+5], cl
0x1400060f0  movzx   ecx, byte ptr [r10+5]
0x1400060f5  mov     byte ptr [rsp+88h+arg_8+4], cl
0x1400060fc  movzx   ecx, byte ptr [r10+6]
0x140006101  mov     byte ptr [rsp+88h+arg_8+3], cl
0x140006108  movzx   ecx, byte ptr [r10+7]
0x14000610d  mov     byte ptr [rsp+88h+arg_8+2], cl
0x140006114  movzx   ecx, byte ptr [r10+8]
0x140006119  mov     byte ptr [rsp+88h+arg_8+1], cl
0x140006120  movzx   ecx, byte ptr [r10+9]
0x140006125  mov     byte ptr [rsp+88h+arg_8], cl
0x14000612c  movzx   ecx, byte ptr [r10+0Ah]
0x140006131  mov     byte ptr [rsp+88h+arg_0+3], cl
0x140006138  movzx   ecx, byte ptr [r10+0Bh]
0x14000613d  mov     byte ptr [rsp+88h+arg_0+2], cl
0x140006144  movzx   ecx, byte ptr [r10+0Ch]
0x140006149  mov     byte ptr [rsp+88h+arg_0+1], cl
0x140006150  movzx   ecx, byte ptr [r10+0Dh]
0x140006155  mov     byte ptr [rsp+88h+arg_0], cl
0x14000615c  jmp     loc_140005E7B
0x140006161  lea     rcx, [rsi+38h]
0x140006165  cmp     rcx, rdi
0x140006168  ja      loc_140005DE5
0x14000616e  xor     ecx, ecx
0x140006170  cmp     [r15+0Ah], r10b
0x140006174  jbe     loc_140005DEF
0x14000617a  lea     r10, [r15+18h]
0x14000617e  jmp     loc_140005DEF
0x140006183  lea     rdx, [r12+38h]
0x140006188  jmp     loc_140005FD8
0x14000618d  test    byte ptr cs:WPP_MAIN_CB.Queue+39h, 20h
0x140006194  jz      loc_140005F28
0x14000619a  mov     [rsp+88h+var_40], al
0x14000619e  mov     [rsp+88h+var_48], rdx
0x1400061a3  lea     rdx, EventLowMemoryWriteRequest
0x1400061aa  jmp     loc_140005EF5
0x1400061af  test    byte ptr cs:WPP_MAIN_CB.Queue+39h, 10h
0x1400061b6  jz      loc_140005F28
0x1400061bc  mov     [rsp+88h+var_40], al
0x1400061c0  mov     [rsp+88h+var_48], rdx
0x1400061c5  lea     rdx, EventLowMemoryReadRequest
0x1400061cc  jmp     loc_140005EF5
```
