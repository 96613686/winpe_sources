# SendToDisplayDriverEx

- ea: `0x1400314e4`
- end: `0x14003167c`
- name: `SendToDisplayDriverEx`
- size: `408`
- prototype: `__int64 __usercall@<rax>(int iEscape@<ecx>, int cjInput@<edx>, LPCSTR lpInData@<r8>, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400318e8`

## callees

- `0x140005704`
- `0x14000cae0`
- `0x1400314e4`
- `0x140031a50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140031585`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140031585`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031523`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400315df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003160c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031523`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400315df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003160c`
- `GDI32!ExtEscape` at `0x1400315a7`
- `GDI32!ExtEscape` at `0x1400315a7`
- `GDI32!DeleteDC` at `0x1400315b2`
- `GDI32!DeleteDC` at `0x1400315b2`
- `GDI32!CreateDCW` at `0x140031515`
- `GDI32!CreateDCW` at `0x140031515`

## pseudocode

```c
__int64 __fastcall SendToDisplayDriverEx(
        int iEscape,
        int cjInput,
        LPCSTR lpInData,
        __int64 a4,
        int a5,
        const WCHAR *a6)
{
  const WCHAR *v8; // rcx
  const WCHAR *v10; // rdx
  HDC DCW; // rbx
  signed int LastError; // ebx
  int v13; // edi
  __int64 v14; // rbx
  DWORD v15; // eax

  v8 = a6;
  if ( a6 )
  {
    v10 = a6;
  }
  else
  {
    v10 = 0;
    v8 = L"DISPLAY";
  }
  DCW = CreateDCW(v8, v10, 0, 0);
  if ( !DCW )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        &WPP_42a33f02ea92324bb459c59c3f9ce2d6_Traceguids,
        0xFFFFFFFFLL,
        LastError);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      return (unsigned int)-2147467259;
    return (unsigned int)LastError;
  }
  SetLastError(0);
  v13 = ExtEscape(DCW, iEscape, cjInput, lpInData, 0, 0);
  DeleteDC(DCW);
  if ( !v13 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v15 = GetLastError();
      WPP_SF_DdD(v14, 11, &WPP_42a33f02ea92324bb459c59c3f9ce2d6_Traceguids, 0xFFFFFFFFLL, iEscape, v15);
    }
    return (unsigned int)-2147467263;
  }
  if ( v13 >= 0 )
    return 0;
  LastError = GetLastError();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_DDdD(*((_QWORD *)WPP_GLOBAL_Control + 2));
  }
  if ( v13 == -1002 )
  {
    LOWORD(LastError) = 4312;
    return (unsigned __int16)LastError | 0x80070000;
  }
  if ( !LastError )
    return (unsigned int)-2147467259;
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1400314e4  push    rbx
0x1400314e6  push    rbp
0x1400314e7  push    rsi
0x1400314e8  push    rdi
0x1400314e9  sub     rsp, 48h
0x1400314ed  mov     rdi, r8
0x1400314f0  mov     esi, ecx
0x1400314f2  mov     rcx, [rsp+68h+arg_28]
0x1400314fa  xor     r8d, r8d; pszPort
0x1400314fd  xor     r9d, r9d; pdm
0x140031500  mov     ebp, edx
0x140031502  test    rcx, rcx
0x140031505  jz      short loc_14003150C
0x140031507  mov     rdx, rcx
0x14003150a  jmp     short loc_140031515
0x14003150c  xor     edx, edx; pwszDevice
0x14003150e  lea     rcx, pwszDriver; "DISPLAY"
0x140031515  call    cs:__imp_CreateDCW
0x14003151b  mov     rbx, rax
0x14003151e  test    rax, rax
0x140031521  jnz     short loc_140031583
0x140031523  call    cs:__imp_GetLastError
0x140031529  mov     ebx, eax
0x14003152b  mov     rcx, cs:WPP_GLOBAL_Control
0x140031532  lea     rax, WPP_GLOBAL_Control
0x140031539  cmp     rcx, rax
0x14003153c  jz      short loc_140031567
0x14003153e  test    byte ptr [rcx+1Ch], 8
0x140031542  jz      short loc_140031567
0x140031544  cmp     byte ptr [rcx+19h], 2
0x140031548  jb      short loc_140031567
0x14003154a  mov     rcx, [rcx+10h]
0x14003154e  lea     r8, WPP_42a33f02ea92324bb459c59c3f9ce2d6_Traceguids
0x140031555  mov     edx, 0Ah
0x14003155a  mov     [rsp+68h+cjOutput], ebx
0x14003155e  or      r9d, 0FFFFFFFFh
0x140031562  call    WPP_SF_Dd
0x140031567  test    ebx, ebx
0x140031569  jle     short loc_140031574
0x14003156b  movzx   ebx, bx
0x14003156e  or      ebx, 80070000h
0x140031574  test    ebx, ebx
0x140031576  mov     eax, 80004005h
0x14003157b  cmovns  ebx, eax
0x14003157e  jmp     loc_140031671
0x140031583  xor     ecx, ecx; dwErrCode
0x140031585  call    cs:__imp_SetLastError
0x14003158b  mov     r9, rdi; lpInData
0x14003158e  mov     [rsp+68h+lpOutData], 0; lpOutData
0x140031597  mov     r8d, ebp; cjInput
0x14003159a  mov     [rsp+68h+cjOutput], 0; cjOutput
0x1400315a2  mov     edx, esi; iEscape
0x1400315a4  mov     rcx, rbx; hdc
0x1400315a7  call    cs:__imp_ExtEscape
0x1400315ad  mov     rcx, rbx; hdc
0x1400315b0  mov     edi, eax
0x1400315b2  call    cs:__imp_DeleteDC
0x1400315b8  test    edi, edi
0x1400315ba  jnz     short loc_14003160A
0x1400315bc  mov     rbx, cs:WPP_GLOBAL_Control
0x1400315c3  lea     rax, WPP_GLOBAL_Control
0x1400315ca  cmp     rbx, rax
0x1400315cd  jz      short loc_140031603
0x1400315cf  test    byte ptr [rbx+1Ch], 1
0x1400315d3  jz      short loc_140031603
0x1400315d5  cmp     byte ptr [rbx+19h], 2
0x1400315d9  jb      short loc_140031603
0x1400315db  mov     rbx, [rbx+10h]
0x1400315df  call    cs:__imp_GetLastError
0x1400315e5  mov     dword ptr [rsp+68h+lpOutData], eax
0x1400315e9  lea     edx, [rdi+0Bh]
0x1400315ec  or      r9d, 0FFFFFFFFh
0x1400315f0  mov     [rsp+68h+cjOutput], esi
0x1400315f4  lea     r8, WPP_42a33f02ea92324bb459c59c3f9ce2d6_Traceguids
0x1400315fb  mov     rcx, rbx
0x1400315fe  call    WPP_SF_DdD
0x140031603  mov     ebx, 80004001h
0x140031608  jmp     short loc_140031671
0x14003160a  jns     short loc_14003166F
0x14003160c  call    cs:__imp_GetLastError
0x140031612  mov     ebx, eax
0x140031614  mov     rcx, cs:WPP_GLOBAL_Control
0x14003161b  lea     rax, WPP_GLOBAL_Control
0x140031622  cmp     rcx, rax
0x140031625  jz      short loc_140031648
0x140031627  test    byte ptr [rcx+1Ch], 1
0x14003162b  jz      short loc_140031648
0x14003162d  cmp     byte ptr [rcx+19h], 5
0x140031631  jb      short loc_140031648
0x140031633  mov     rcx, [rcx+10h]
0x140031637  mov     [rsp+68h+var_38], ebx
0x14003163b  mov     dword ptr [rsp+68h+lpOutData], edi
0x14003163f  mov     [rsp+68h+cjOutput], esi
0x140031643  call    WPP_SF_DDdD
0x140031648  cmp     edi, 0FFFFFC16h
0x14003164e  jnz     short loc_140031657
0x140031650  mov     ebx, 10D8h
0x140031655  jmp     short loc_14003165D
0x140031657  test    ebx, ebx
0x140031659  jz      short loc_140031668
0x14003165b  jle     short loc_140031671
0x14003165d  movzx   ebx, bx
0x140031660  or      ebx, 80070000h
0x140031666  jmp     short loc_140031671
0x140031668  mov     ebx, 80004005h
0x14003166d  jmp     short loc_140031671
0x14003166f  xor     ebx, ebx
0x140031671  mov     eax, ebx
0x140031673  add     rsp, 48h
0x140031677  pop     rdi
0x140031678  pop     rsi
0x140031679  pop     rbp
0x14003167a  pop     rbx
0x14003167b  retn
```
