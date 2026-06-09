# CADMCOMW::NormalizeMDPath(ushort const *,ulong,ushort *,ulong,ulong *)

- ea: `0x1800076b8`
- end: `0x1800078a4`
- name: `?NormalizeMDPath@CADMCOMW@@AEAAJPEBGKPEAGKPEAK@Z`
- size: `492`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180003590`

## callees

- `0x1800076b8`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x180007714`
- `IisRTL!PuDbgPrint` at `0x1800077e6`
- `IisRTL!PuDbgPrint` at `0x18000788d`
- `IisRTL!PuDbgPrint` at `0x180007714`
- `IisRTL!PuDbgPrint` at `0x1800077e6`
- `IisRTL!PuDbgPrint` at `0x18000788d`

## string_xrefs

- `0x180007708`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x1800077d4`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180007860`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x1800076ea`: `Normalizing the path %S into buffer with length %d.\n`
- `0x1800076f6`: `CADMCOMW::NormalizeMDPath`
- `0x1800077c8`: `CADMCOMW::NormalizeMDPath`
- `0x180007854`: `CADMCOMW::NormalizeMDPath`
- `0x1800077bc`: `The input path %S cannot fit the output buffer with length %d.\n`
- `0x180007871`: `Normalizing the path %S %s with 0x%08x and the normalized path is %S with length %d.\n`

## pseudocode

```c
__int64 __fastcall CADMCOMW::NormalizeMDPath(
        CADMCOMW *this,
        const unsigned __int16 *a2,
        int a3,
        unsigned __int16 *a4,
        unsigned int a5,
        unsigned int *a6)
{
  char v8; // r9
  int v10; // ebx
  int v11; // r10d
  __int64 v12; // rdx
  unsigned __int16 v13; // cx
  bool v14; // zf
  __int64 v15; // rax
  const char *v16; // r8

  v8 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
      8469,
      "CADMCOMW::NormalizeMDPath",
      "Normalizing the path %S into buffer with length %d.\n",
      a2,
      514);
    v8 = g_dwDebugFlags;
  }
  if ( a6 )
    *a6 = 0;
  if ( !a4 || (*a4 = 0, !a2) )
  {
LABEL_6:
    v10 = -2147024809;
    goto LABEL_32;
  }
  v11 = 0;
  LODWORD(v12) = 0;
  while ( 1 )
  {
    v13 = a2[(unsigned int)v12];
    if ( (_DWORD)v12 - a3 == 1 )
      v11 = 1;
    if ( v13 != 92 && v13 != 47 )
    {
      if ( (unsigned __int16)(v13 - 97) > 0x19u )
      {
        a4[(unsigned int)v12] = v13;
        if ( !v13 )
          goto LABEL_26;
      }
      else
      {
        a4[(unsigned int)v12] = v13 - 32;
      }
      goto LABEL_18;
    }
    a4[(unsigned int)v12] = 47;
    if ( v11 )
      break;
LABEL_18:
    LODWORD(v12) = v12 + 1;
    if ( (unsigned int)v12 >= 0x202 )
    {
      v14 = (_DWORD)v12 == 514;
      goto LABEL_20;
    }
  }
  v12 = (unsigned int)(v12 + 1);
  v14 = (_DWORD)v12 == 514;
  if ( (unsigned int)v12 >= 0x202 )
  {
LABEL_20:
    if ( !v14 )
      goto LABEL_27;
    if ( (v8 & 3) != 0 )
    {
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
        8567,
        "CADMCOMW::NormalizeMDPath",
        "The input path %S cannot fit the output buffer with length %d.\n",
        a2,
        514);
      v8 = g_dwDebugFlags;
    }
    goto LABEL_23;
  }
  a4[v12] = 0;
LABEL_26:
  if ( (_DWORD)v12 )
  {
LABEL_27:
    if ( a4[(unsigned int)(v12 - 1)] != 47 )
    {
      v15 = (unsigned int)v12;
      v12 = (unsigned int)(v12 + 1);
      a4[v15] = 47;
      if ( (_DWORD)v12 != 514 )
      {
        a4[v12] = 0;
        goto LABEL_30;
      }
LABEL_23:
      *a4 = 0;
      goto LABEL_6;
    }
  }
LABEL_30:
  v10 = 0;
  if ( a6 )
    *a6 = v12 + 1;
LABEL_32:
  if ( (v8 & 3) != 0 )
  {
    v16 = "failed";
    if ( v10 >= 0 )
      v16 = "succeeded";
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
      8621,
      "CADMCOMW::NormalizeMDPath",
      "Normalizing the path %S %s with 0x%08x and the normalized path is %S with length %d.\n",
      a2,
      v16,
      v10,
      a4,
      *a6);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800076b8  push    rbx
0x1800076ba  push    rbp
0x1800076bb  push    rsi
0x1800076bc  push    rdi
0x1800076bd  push    r12
0x1800076bf  push    r14
0x1800076c1  push    r15
0x1800076c3  sub     rsp, 50h
0x1800076c7  mov     rdi, r9
0x1800076ca  mov     ebx, r8d
0x1800076cd  mov     r9d, cs:g_dwDebugFlags
0x1800076d4  mov     r14, rdx
0x1800076d7  mov     r15d, 202h
0x1800076dd  test    r9b, 3
0x1800076e1  jz      short loc_180007721
0x1800076e3  mov     rcx, cs:g_pDebug
0x1800076ea  lea     rax, aNormalizingThe_0; "Normalizing the path %S into buffer wit"...
0x1800076f1  mov     dword ptr [rsp+88h+var_58], r15d
0x1800076f6  lea     r9, aCadmcomwNormal; "CADMCOMW::NormalizeMDPath"
0x1800076fd  mov     [rsp+88h+var_60], rdx
0x180007702  mov     r8d, 2115h
0x180007708  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x18000770f  mov     [rsp+88h+var_68], rax
0x180007714  call    cs:__imp_PuDbgPrint
0x18000771a  mov     r9d, cs:g_dwDebugFlags
0x180007721  mov     rsi, [rsp+88h+arg_28]
0x180007729  xor     ebp, ebp
0x18000772b  test    rsi, rsi
0x18000772e  jz      short loc_180007732
0x180007730  mov     [rsi], ebp
0x180007732  test    rdi, rdi
0x180007735  jnz     short loc_180007741
0x180007737  mov     ebx, 80070057h
0x18000773c  jmp     loc_180007833
0x180007741  mov     [rdi], bp
0x180007744  test    r14, r14
0x180007747  jz      short loc_180007737
0x180007749  mov     r12d, 1
0x18000774f  mov     r10d, ebp
0x180007752  mov     edx, ebp
0x180007754  lea     r11d, [r12+2Eh]
0x180007759  mov     eax, edx
0x18000775b  mov     r8d, edx
0x18000775e  sub     eax, ebx
0x180007760  cmp     eax, r12d
0x180007763  movzx   ecx, word ptr [r14+r8*2]
0x180007768  cmovz   r10d, r12d
0x18000776c  cmp     cx, 5Ch ; '\'
0x180007770  jz      short loc_180007798
0x180007772  cmp     cx, r11w
0x180007776  jz      short loc_180007798
0x180007778  lea     eax, [rcx-61h]
0x18000777b  cmp     ax, 19h
0x18000777f  ja      short loc_18000778C
0x180007781  sub     cx, 20h ; ' '
0x180007785  mov     [rdi+r8*2], cx
0x18000778a  jmp     short loc_1800077A2
0x18000778c  mov     [rdi+r8*2], cx
0x180007791  test    cx, cx
0x180007794  jz      short loc_180007807
0x180007796  jmp     short loc_1800077A2
0x180007798  mov     [rdi+r8*2], r11w
0x18000779d  test    r10d, r10d
0x1800077a0  jnz     short loc_1800077FB
0x1800077a2  add     edx, r12d
0x1800077a5  cmp     edx, r15d
0x1800077a8  jb      short loc_180007759
0x1800077aa  cmp     edx, r15d
0x1800077ad  jnz     short loc_18000780B
0x1800077af  test    r9b, 3
0x1800077b3  jz      short loc_1800077F3
0x1800077b5  mov     rcx, cs:g_pDebug
0x1800077bc  lea     rax, aTheInputPathSC; "The input path %S cannot fit the output"...
0x1800077c3  mov     dword ptr [rsp+88h+var_58], r15d
0x1800077c8  lea     r9, aCadmcomwNormal; "CADMCOMW::NormalizeMDPath"
0x1800077cf  mov     [rsp+88h+var_60], r14
0x1800077d4  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x1800077db  mov     r8d, 2177h
0x1800077e1  mov     [rsp+88h+var_68], rax
0x1800077e6  call    cs:__imp_PuDbgPrint
0x1800077ec  mov     r9d, cs:g_dwDebugFlags
0x1800077f3  mov     [rdi], bp
0x1800077f6  jmp     loc_180007737
0x1800077fb  add     edx, r12d
0x1800077fe  cmp     edx, r15d
0x180007801  jnb     short loc_1800077AD
0x180007803  mov     [rdi+rdx*2], bp
0x180007807  test    edx, edx
0x180007809  jz      short loc_180007827
0x18000780b  lea     eax, [rdx-1]
0x18000780e  cmp     [rdi+rax*2], r11w
0x180007813  jz      short loc_180007827
0x180007815  mov     eax, edx
0x180007817  inc     edx
0x180007819  mov     [rdi+rax*2], r11w
0x18000781e  cmp     edx, r15d
0x180007821  jz      short loc_1800077F3
0x180007823  mov     [rdi+rdx*2], bp
0x180007827  mov     ebx, ebp
0x180007829  test    rsi, rsi
0x18000782c  jz      short loc_180007833
0x18000782e  lea     eax, [rdx+1]
0x180007831  mov     [rsi], eax
0x180007833  test    r9b, 3
0x180007837  jz      short loc_180007893
0x180007839  mov     ecx, [rsi]
0x18000783b  lea     rax, aSucceeded; "succeeded"
0x180007842  mov     [rsp+88h+var_40], ecx
0x180007846  lea     r8, aFailed; "failed"
0x18000784d  mov     rcx, cs:g_pDebug
0x180007854  lea     r9, aCadmcomwNormal; "CADMCOMW::NormalizeMDPath"
0x18000785b  mov     [rsp+88h+var_48], rdi
0x180007860  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x180007867  mov     [rsp+88h+var_50], ebx
0x18000786b  test    ebx, ebx
0x18000786d  cmovns  r8, rax
0x180007871  lea     rax, aNormalizingThe; "Normalizing the path %S %s with 0x%08x "...
0x180007878  mov     [rsp+88h+var_58], r8
0x18000787d  mov     r8d, 21ADh
0x180007883  mov     [rsp+88h+var_60], r14
0x180007888  mov     [rsp+88h+var_68], rax
0x18000788d  call    cs:__imp_PuDbgPrint
0x180007893  mov     eax, ebx
0x180007895  add     rsp, 50h
0x180007899  pop     r15
0x18000789b  pop     r14
0x18000789d  pop     r12
0x18000789f  pop     rdi
0x1800078a0  pop     rsi
0x1800078a1  pop     rbp
0x1800078a2  pop     rbx
0x1800078a3  retn
```
