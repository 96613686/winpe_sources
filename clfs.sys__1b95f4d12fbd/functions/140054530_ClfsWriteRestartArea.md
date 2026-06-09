# ClfsWriteRestartArea

- ea: `0x140054530`
- end: `0x1400548bb`
- name: `ClfsWriteRestartArea`
- size: `907`
- prototype: `NTSTATUS __stdcall(PVOID pvMarshalContext, PVOID pvRestartBuffer, ULONG cbRestartBuffer, PCLFS_LSN plsnBase, ULONG fFlags, PULONG pcbWritten, PCLFS_LSN plsnNext)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14000ed64`
- `0x140011d90`
- `0x140054530`
- `0x1400548c4`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140054608`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140054608`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005469e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400795d9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005469e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400795d9`

## string_xrefs

- `0x140054686`: `ClfsWriteRestartArea`
- `0x1400546f4`: `ClfsWriteRestartArea`
- `0x140054755`: `ClfsWriteRestartArea`
- `0x140054860`: `ClfsWriteRestartArea`
- `0x14005489f`: `ClfsWriteRestartArea`

## pseudocode

```c
NTSTATUS __stdcall ClfsWriteRestartArea(
        PVOID pvMarshalContext,
        PVOID pvRestartBuffer,
        ULONG cbRestartBuffer,
        PCLFS_LSN plsnBase,
        ULONG fFlags,
        PULONG pcbWritten,
        PCLFS_LSN plsnNext)
{
  CLFS_LSN v11; // r10
  ULONG v12; // r15d
  NTSTATUS v14; // edi
  unsigned int *v15; // [rsp+28h] [rbp-60h]
  union _CLS_LSN v16; // [rsp+48h] [rbp-40h] BYREF
  union _CLS_LSN v17; // [rsp+50h] [rbp-38h] BYREF
  unsigned int v18; // [rsp+90h] [rbp+8h] BYREF

  v11 = CLFS_LSN_INVALID;
  v16 = CLFS_LSN_INVALID;
  v17 = CLFS_LSN_NULL;
  v18 = 0;
  if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      180,
      (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
      (unsigned int)"ClfsWriteRestartArea",
      39);
    v11 = CLFS_LSN_INVALID;
  }
  if ( !pvMarshalContext )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        181,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsWriteRestartArea",
        47,
        -1073741811);
    }
    return -1073741811;
  }
  v12 = fFlags;
  if ( (fFlags & 0xFFFFFFFB) != 0 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        182,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsWriteRestartArea",
        58,
        -1073741811);
    }
    return -1073741811;
  }
  if ( plsnBase )
  {
    if ( v11.ullOffset == plsnBase->ullOffset )
    {
      if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
      {
        WPP_SF_slD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          183,
          (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
          (unsigned int)"ClfsWriteRestartArea",
          76,
          -1073741811);
      }
      return -1073741811;
    }
    v16 = *plsnBase;
  }
  if ( !cbRestartBuffer )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        184,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsWriteRestartArea",
        90,
        -1073741811);
    }
    return -1073741811;
  }
  if ( pvRestartBuffer )
  {
    if ( *(_DWORD *)pvMarshalContext == -1040322550 && *((_DWORD *)pvMarshalContext + 1) == 200 )
    {
      KeEnterCriticalRegion();
      v14 = CClfsKernelMarshallingContext::WriteRestartArea(
              (CClfsKernelMarshallingContext *)pvMarshalContext,
              pvRestartBuffer,
              cbRestartBuffer,
              &v16,
              v12,
              &v18,
              &v17);
      if ( v14 < 0
        && WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
      {
        LODWORD(v15) = v14;
        WPP_SF_slD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          187,
          (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
          (unsigned int)"ClfsWriteRestartArea",
          157,
          v15);
      }
      KeLeaveCriticalRegion();
      if ( pcbWritten && v14 >= 0 )
        *pcbWritten = v18;
      if ( plsnNext )
      {
        if ( v14 < 0 )
          return v14;
        *plsnNext = v17;
      }
      if ( v14 >= 0
        && WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          188,
          (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
          (unsigned int)"ClfsWriteRestartArea",
          199);
      }
      return v14;
    }
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        186,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsWriteRestartArea",
        119,
        -1073741811);
    }
    return -1073741811;
  }
  if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
  {
    WPP_SF_slD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      185,
      (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
      (unsigned int)"ClfsWriteRestartArea",
      102,
      -1073741811);
  }
  return -1073741592;
}

```

## disassembly

```asm
0x140054530  mov     r11, rsp
0x140054533  mov     [r11+10h], rbx
0x140054537  mov     [r11+18h], rsi
0x14005453b  push    rdi
0x14005453c  push    r12
0x14005453e  push    r13
0x140054540  push    r14
0x140054542  push    r15
0x140054544  sub     rsp, 60h
0x140054548  mov     r14, r9
0x14005454b  mov     r12d, r8d
0x14005454e  mov     r13, rdx
0x140054551  mov     rdi, rcx
0x140054554  mov     r10, qword ptr cs:CLFS_LSN_INVALID
0x14005455b  mov     [r11-40h], r10
0x14005455f  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x140054566  mov     [r11-38h], rax
0x14005456a  mov     dword ptr [r11+8], 0
0x140054572  lea     rsi, WPP_GLOBAL_Control
0x140054579  mov     rcx, cs:WPP_GLOBAL_Control
0x140054580  mov     ebx, 4000000h
0x140054585  cmp     rcx, rsi
0x140054588  jnz     loc_1400546DC
0x14005458e  test    rdi, rdi
0x140054591  jz      loc_1400547A4
0x140054597  mov     r15d, [rsp+88h+fFlags]
0x14005459f  test    r15d, 0FFFFFFFBh
0x1400545a6  jnz     loc_1400547D7
0x1400545ac  test    r14, r14
0x1400545af  jnz     loc_140054717
0x1400545b5  test    r12d, r12d
0x1400545b8  jz      loc_14005480A
0x1400545be  test    r13, r13
0x1400545c1  jz      loc_14005483A
0x1400545c7  cmp     dword ptr [rdi], 0C1FDF00Ah
0x1400545cd  jz      short loc_1400545FF
0x1400545cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400545d6  cmp     rcx, rsi
0x1400545d9  jnz     loc_140054881
0x1400545df  mov     eax, 0C000000Dh
0x1400545e4  lea     r11, [rsp+88h+var_28]
0x1400545e9  mov     rbx, [r11+38h]
0x1400545ed  mov     rsi, [r11+40h]
0x1400545f1  mov     rsp, r11
0x1400545f4  pop     r15
0x1400545f6  pop     r14
0x1400545f8  pop     r13
0x1400545fa  pop     r12
0x1400545fc  pop     rdi
0x1400545fd  retn
0x1400545ff  cmp     dword ptr [rdi+4], 0C8h
0x140054606  jnz     short loc_1400545CF
0x140054608  call    cs:__imp_KeEnterCriticalRegion
0x14005460f  nop     dword ptr [rax+rax+00h]
0x140054614  nop
0x140054615  lea     rax, [rsp+88h+var_38]
0x14005461a  mov     [rsp+88h+var_58], rax; union _CLS_LSN *
0x14005461f  lea     rax, [rsp+88h+arg_0]
0x140054627  mov     [rsp+88h+var_60], rax; unsigned int *
0x14005462c  mov     [rsp+88h+var_68], r15d; unsigned int
0x140054631  lea     r9, [rsp+88h+var_40]; union _CLS_LSN *
0x140054636  mov     r8d, r12d; unsigned int
0x140054639  mov     rdx, r13; void *
0x14005463c  mov     rcx, rdi; this
0x14005463f  call    ?WriteRestartArea@CClfsKernelMarshallingContext@@QEAAJPEAXKAEBT_CLS_LSN@@KAEAKAEAT2@@Z; CClfsKernelMarshallingContext::WriteRestartArea(void *,ulong,_CLS_LSN const &,ulong,ulong &,_CLS_LSN &)
0x140054644  mov     edi, eax
0x140054646  mov     [rsp+88h+var_48], eax
0x14005464a  jmp     short loc_14005465E
0x14005464c  mov     edi, eax
0x14005464e  mov     [rsp+88h+var_48], eax
0x140054652  lea     rsi, WPP_GLOBAL_Control
0x140054659  mov     ebx, 4000000h
0x14005465e  test    edi, edi
0x140054660  jns     short loc_14005469E
0x140054662  mov     rcx, cs:WPP_GLOBAL_Control
0x140054669  cmp     rcx, rsi
0x14005466c  jz      short loc_14005469E
0x14005466e  mov     eax, [rcx+2Ch]
0x140054671  test    ebx, eax
0x140054673  jz      short loc_14005469E
0x140054675  mov     edx, 0BBh
0x14005467a  mov     dword ptr [rsp+88h+var_60], edi
0x14005467e  mov     [rsp+88h+var_68], 159Dh
0x140054686  lea     r9, aClfswriteresta_0; "ClfsWriteRestartArea"
0x14005468d  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x140054694  mov     rcx, [rcx+18h]
0x140054698  call    WPP_SF_slD
0x14005469d  nop
0x14005469e  call    cs:__imp_KeLeaveCriticalRegion
0x1400546a5  nop     dword ptr [rax+rax+00h]
0x1400546aa  mov     rcx, [rsp+88h+pcbWritten]
0x1400546b2  test    rcx, rcx
0x1400546b5  jz      short loc_1400546C4
0x1400546b7  test    edi, edi
0x1400546b9  js      short loc_1400546C4
0x1400546bb  mov     eax, [rsp+88h+arg_0]
0x1400546c2  mov     [rcx], eax
0x1400546c4  mov     rcx, [rsp+88h+plsnNext]
0x1400546cc  test    rcx, rcx
0x1400546cf  jnz     short loc_140054729
0x1400546d1  test    edi, edi
0x1400546d3  jns     short loc_140054737
0x1400546d5  mov     eax, edi
0x1400546d7  jmp     loc_1400545E4
0x1400546dc  mov     eax, [rcx+2Ch]
0x1400546df  test    ebx, eax
0x1400546e1  jz      loc_14005458E
0x1400546e7  mov     edx, 0B4h
0x1400546ec  mov     [rsp+88h+var_68], 1527h
0x1400546f4  lea     r9, aClfswriteresta_0; "ClfsWriteRestartArea"
0x1400546fb  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x140054702  mov     rcx, [rcx+18h]
0x140054706  call    WPP_SF_sd
0x14005470b  mov     r10, qword ptr cs:CLFS_LSN_INVALID
0x140054712  jmp     loc_14005458E
0x140054717  mov     rax, [r14]
0x14005471a  cmp     r10, rax
0x14005471d  jz      short loc_140054771
0x14005471f  mov     qword ptr [rsp+88h+var_40], rax
0x140054724  jmp     loc_1400545B5
0x140054729  test    edi, edi
0x14005472b  js      short loc_1400546D5
0x14005472d  mov     rax, qword ptr [rsp+88h+var_38]
0x140054732  mov     [rcx], rax
0x140054735  jmp     short loc_1400546D1
0x140054737  mov     rcx, cs:WPP_GLOBAL_Control
0x14005473e  cmp     rcx, rsi
0x140054741  jz      short loc_1400546D5
0x140054743  test    [rcx+2Ch], ebx
0x140054746  jz      short loc_1400546D5
0x140054748  mov     edx, 0BCh
0x14005474d  mov     [rsp+88h+var_68], 15C7h
0x140054755  lea     r9, aClfswriteresta_0; "ClfsWriteRestartArea"
0x14005475c  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x140054763  mov     rcx, [rcx+18h]
0x140054767  call    WPP_SF_sd
0x14005476c  jmp     loc_1400546D5
0x140054771  mov     rcx, cs:WPP_GLOBAL_Control
0x140054778  cmp     rcx, rsi
0x14005477b  jz      loc_1400545DF
0x140054781  test    [rcx+2Ch], ebx
0x140054784  jz      loc_1400545DF
0x14005478a  mov     edx, 0B7h
0x14005478f  mov     dword ptr [rsp+88h+var_60], 0C000000Dh
0x140054797  mov     [rsp+88h+var_68], 154Ch
0x14005479f  jmp     loc_14005489F
0x1400547a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400547ab  cmp     rcx, rsi
0x1400547ae  jz      loc_1400545DF
0x1400547b4  test    [rcx+2Ch], ebx
0x1400547b7  jz      loc_1400545DF
0x1400547bd  mov     edx, 0B5h
0x1400547c2  mov     dword ptr [rsp+88h+var_60], 0C000000Dh
0x1400547ca  mov     [rsp+88h+var_68], 152Fh
0x1400547d2  jmp     loc_14005489F
0x1400547d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400547de  cmp     rcx, rsi
0x1400547e1  jz      loc_1400545DF
0x1400547e7  test    [rcx+2Ch], ebx
0x1400547ea  jz      loc_1400545DF
0x1400547f0  mov     edx, 0B6h
0x1400547f5  mov     dword ptr [rsp+88h+var_60], 0C000000Dh
0x1400547fd  mov     [rsp+88h+var_68], 153Ah
0x140054805  jmp     loc_14005489F
0x14005480a  mov     rcx, cs:WPP_GLOBAL_Control
0x140054811  cmp     rcx, rsi
0x140054814  jz      loc_1400545DF
0x14005481a  test    [rcx+2Ch], ebx
0x14005481d  jz      loc_1400545DF
0x140054823  mov     edx, 0B8h
0x140054828  mov     dword ptr [rsp+88h+var_60], 0C000000Dh
0x140054830  mov     [rsp+88h+var_68], 155Ah
0x140054838  jmp     short loc_14005489F
0x14005483a  mov     rcx, cs:WPP_GLOBAL_Control
0x140054841  cmp     rcx, rsi
0x140054844  jz      short loc_140054877
0x140054846  test    [rcx+2Ch], ebx
0x140054849  jz      short loc_140054877
0x14005484b  mov     edx, 0B9h
0x140054850  mov     dword ptr [rsp+88h+var_60], 0C000000Dh
0x140054858  mov     [rsp+88h+var_68], 1566h
0x140054860  lea     r9, aClfswriteresta_0; "ClfsWriteRestartArea"
0x140054867  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14005486e  mov     rcx, [rcx+18h]
0x140054872  call    WPP_SF_slD
0x140054877  mov     eax, 0C00000E8h
0x14005487c  jmp     loc_1400545E4
0x140054881  test    [rcx+2Ch], ebx
0x140054884  jz      loc_1400545DF
0x14005488a  mov     edx, 0BAh
0x14005488f  mov     dword ptr [rsp+88h+var_60], 0C000000Dh
0x140054897  mov     [rsp+88h+var_68], 1577h
0x14005489f  lea     r9, aClfswriteresta_0; "ClfsWriteRestartArea"
0x1400548a6  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x1400548ad  mov     rcx, [rcx+18h]
0x1400548b1  call    WPP_SF_slD
0x1400548b6  jmp     loc_1400545DF
0x1400795d0  push    rbp
0x1400795d2  sub     rsp, 40h
0x1400795d6  mov     rbp, rdx
0x1400795d9  call    cs:__imp_KeLeaveCriticalRegion
0x1400795e0  nop     dword ptr [rax+rax+00h]
0x1400795e5  nop
0x1400795e6  add     rsp, 40h
0x1400795ea  pop     rbp
0x1400795eb  retn
```
