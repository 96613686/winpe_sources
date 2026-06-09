# XLOLENameUpdate(x,x,x,x,x,x)

- ea: `0x1001fe30`
- end: `0x100200b2`
- name: `_XLOLENameUpdate@24`
- size: `642`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x1001d870`

## callees

- `0x1001fd20`
- `0x1001fe30`
- `0x10021260`
- `0x10021330`
- `0x10022320`
- `0x10035510`
- `0x100358c5`
- `0x10035e9f`

## pseudocode

```c
int __fastcall XLOLENameUpdate(int a1, int a2, _WORD *a3, unsigned __int16 a4, unsigned __int16 a5, int a6)
{
  const wchar_t *v6; // esi
  _WORD *v7; // ecx
  int v8; // eax
  int v9; // edx
  _WORD *v10; // eax
  int v11; // ecx
  _WORD *v12; // eax
  int v13; // edx
  bool v15; // zf
  int v16; // ecx
  int v17; // eax
  _WORD *v18; // edx
  _WORD *v19; // eax
  int v20; // ecx
  _WORD *v21; // eax
  int v22; // edx
  int v23; // eax
  int v24; // ecx
  const wchar_t *v25; // edi
  _WORD *v26; // edx
  _WORD *v27; // eax
  int v28; // ecx
  _WORD *v29; // eax
  int v30; // edi
  int v31; // eax
  _WORD *v32; // ecx
  const wchar_t *v33; // edx
  int v34; // esi
  _WORD *v35; // eax
  DispatchDriver *v36; // esi
  int v38; // [esp+0h] [ebp-ACh] BYREF
  ExcelWorkbook *v39; // [esp+10h] [ebp-9Ch]
  CHAR v40[4]; // [esp+14h] [ebp-98h] BYREF
  DispatchDriver *v41; // [esp+18h] [ebp-94h]
  _WORD v42[62]; // [esp+1Ch] [ebp-90h] BYREF
  int *v43; // [esp+9Ch] [ebp-10h]
  int v44; // [esp+A8h] [ebp-4h]

  v43 = &v38;
  *(_DWORD *)v40 = a2;
  v6 = L"='";
  v39 = *(ExcelWorkbook **)(a1 + 12);
  v7 = v42;
  v41 = 0;
  v8 = 2147483646;
  v9 = 62;
  do
  {
    if ( !v8 )
      break;
    if ( !*v6 )
      break;
    *v7++ = *v6++;
    --v8;
    --v9;
  }
  while ( v9 );
  v10 = v7 - 1;
  if ( v9 )
    v10 = v7;
  *v10 = 0;
  v11 = 62;
  v12 = v42;
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  v13 = v11 != 0 ? 62 - v11 : 0;
  if ( v11 )
  {
    v16 = 62 - v13;
    v15 = v13 == 62;
    v17 = 2147483646;
    v18 = &v42[v13];
    if ( !v15 )
    {
      do
      {
        if ( !v17 )
          break;
        if ( !*a3 )
          break;
        *v18++ = *a3++;
        --v17;
        --v16;
      }
      while ( v16 );
    }
    v19 = v18 - 1;
    if ( v16 )
      v19 = v18;
    *v19 = 0;
  }
  v20 = 62;
  v21 = v42;
  do
  {
    if ( !*v21 )
      break;
    ++v21;
    --v20;
  }
  while ( v20 );
  v22 = v20 != 0 ? 62 - v20 : 0;
  if ( v20 )
  {
    v23 = 2147483646;
    v24 = 62 - v22;
    v15 = v22 == 62;
    v25 = L"'!";
    v26 = &v42[v22];
    if ( !v15 )
    {
      do
      {
        if ( !v23 )
          break;
        if ( !*v25 )
          break;
        *v26++ = *v25++;
        --v23;
        --v24;
      }
      while ( v24 );
    }
    v27 = v26 - 1;
    if ( v24 )
      v27 = v26;
    *v27 = 0;
  }
  AppendCell(a4);
  v28 = 62;
  v29 = v42;
  do
  {
    if ( !*v29 )
      break;
    ++v29;
    --v28;
  }
  while ( v28 );
  v30 = v28 != 0 ? 62 - v28 : 0;
  if ( v28 )
  {
    v31 = 2147483646;
    v32 = &v42[v30];
    v33 = L":";
    v34 = 62 - v30;
    if ( 62 != v30 )
    {
      do
      {
        if ( !v31 )
          break;
        if ( !*v33 )
          break;
        *v32++ = *v33++;
        --v31;
        --v34;
      }
      while ( v34 );
    }
    v35 = v32 - 1;
    if ( v34 )
      v35 = v32;
    *v35 = 0;
  }
  AppendCell(a5);
  v44 = 0;
  v36 = ExcelWorkbook::Names(v39);
  v41 = v36;
  DispatchDriver::InvokeHelper(v36, 181, wInvokeMethod, 0xBu, v40, dword_1003A624, *(_DWORD *)v40, v42, 1);
  if ( v36 )
  {
    DispatchDriver::~DispatchDriver(v36);
    operator delete(v36);
  }
  return 0;
}

```

## disassembly

```asm
0x1001fe30  mov     edi, edi
0x1001fe32  push    ebp
0x1001fe33  mov     ebp, esp
0x1001fe35  push    0FFFFFFFFh
0x1001fe37  push    offset _XLOLENameUpdate@24_SEH
0x1001fe3c  mov     eax, large fs:0
0x1001fe42  push    eax
0x1001fe43  sub     esp, 90h
0x1001fe49  mov     eax, ___security_cookie
0x1001fe4e  xor     eax, ebp
0x1001fe50  mov     [ebp+var_14], eax
0x1001fe53  push    ebx
0x1001fe54  push    esi
0x1001fe55  push    edi
0x1001fe56  push    eax
0x1001fe57  lea     eax, [ebp+var_C]
0x1001fe5a  mov     large fs:0, eax
0x1001fe60  mov     [ebp+var_10], esp
0x1001fe63  mov     dword ptr [ebp+var_98], edx
0x1001fe69  mov     eax, [ecx+0Ch]
0x1001fe6c  mov     esi, offset asc_10005100; "='"
0x1001fe71  mov     [ebp+var_9C], eax
0x1001fe77  lea     ecx, [ebp+var_90]
0x1001fe7d  mov     [ebp+var_94], 0
0x1001fe87  mov     eax, 7FFFFFFEh
0x1001fe8c  mov     edx, 3Eh ; '>'
0x1001fe91  test    eax, eax
0x1001fe93  jz      short loc_1001FEAC
0x1001fe95  movzx   edi, word ptr [esi]
0x1001fe98  test    di, di
0x1001fe9b  jz      short loc_1001FEAC
0x1001fe9d  mov     [ecx], di
0x1001fea0  add     esi, 2
0x1001fea3  add     ecx, 2
0x1001fea6  dec     eax
0x1001fea7  sub     edx, 1
0x1001feaa  jnz     short loc_1001FE91
0x1001feac  lea     eax, [ecx-2]
0x1001feaf  test    edx, edx
0x1001feb1  cmovnz  eax, ecx
0x1001feb4  xor     ecx, ecx
0x1001feb6  mov     [eax], cx
0x1001feb9  mov     ecx, 3Eh ; '>'
0x1001febe  lea     eax, [ebp+var_90]
0x1001fec4  cmp     word ptr [eax], 0
0x1001fec8  jz      short loc_1001FED2
0x1001feca  add     eax, 2
0x1001fecd  sub     ecx, 1
0x1001fed0  jnz     short loc_1001FEC4
0x1001fed2  mov     esi, 3Eh ; '>'
0x1001fed7  mov     edx, ecx
0x1001fed9  mov     eax, esi
0x1001fedb  sub     eax, ecx
0x1001fedd  neg     edx
0x1001fedf  sbb     edx, edx
0x1001fee1  and     edx, eax
0x1001fee3  test    ecx, ecx
0x1001fee5  jz      short loc_1001FF28
0x1001fee7  mov     edi, [ebp+arg_0]
0x1001feea  mov     ecx, esi
0x1001feec  sub     ecx, edx
0x1001feee  mov     eax, 7FFFFFFEh
0x1001fef3  lea     edx, [ebp+edx*2+var_90]
0x1001fefa  jz      short loc_1001FF1B
0x1001fefc  nop     dword ptr [eax+00h]
0x1001ff00  test    eax, eax
0x1001ff02  jz      short loc_1001FF1B
0x1001ff04  movzx   ebx, word ptr [edi]
0x1001ff07  test    bx, bx
0x1001ff0a  jz      short loc_1001FF1B
0x1001ff0c  mov     [edx], bx
0x1001ff0f  add     edi, 2
0x1001ff12  add     edx, 2
0x1001ff15  dec     eax
0x1001ff16  sub     ecx, 1
0x1001ff19  jnz     short loc_1001FF00
0x1001ff1b  test    ecx, ecx
0x1001ff1d  lea     eax, [edx-2]
0x1001ff20  cmovnz  eax, edx
0x1001ff23  xor     ecx, ecx
0x1001ff25  mov     [eax], cx
0x1001ff28  mov     ecx, esi
0x1001ff2a  lea     eax, [ebp+var_90]
0x1001ff30  cmp     word ptr [eax], 0
0x1001ff34  jz      short loc_1001FF3E
0x1001ff36  add     eax, 2
0x1001ff39  sub     ecx, 1
0x1001ff3c  jnz     short loc_1001FF30
0x1001ff3e  mov     eax, esi
0x1001ff40  mov     edx, ecx
0x1001ff42  sub     eax, ecx
0x1001ff44  neg     edx
0x1001ff46  sbb     edx, edx
0x1001ff48  and     edx, eax
0x1001ff4a  test    ecx, ecx
0x1001ff4c  jz      short loc_1001FF8D
0x1001ff4e  mov     ecx, esi
0x1001ff50  mov     eax, 7FFFFFFEh
0x1001ff55  sub     ecx, edx
0x1001ff57  mov     edi, offset asc_10005108; "'!"
0x1001ff5c  lea     edx, [ebp+edx*2+var_90]
0x1001ff63  jz      short loc_1001FF80
0x1001ff65  test    eax, eax
0x1001ff67  jz      short loc_1001FF80
0x1001ff69  movzx   ebx, word ptr [edi]
0x1001ff6c  test    bx, bx
0x1001ff6f  jz      short loc_1001FF80
0x1001ff71  mov     [edx], bx
0x1001ff74  add     edi, 2
0x1001ff77  add     edx, 2
0x1001ff7a  dec     eax
0x1001ff7b  sub     ecx, 1
0x1001ff7e  jnz     short loc_1001FF65
0x1001ff80  test    ecx, ecx
0x1001ff82  lea     eax, [edx-2]
0x1001ff85  cmovnz  eax, edx
0x1001ff88  xor     ecx, ecx
0x1001ff8a  mov     [eax], cx
0x1001ff8d  movzx   eax, [ebp+arg_4]
0x1001ff91  lea     ecx, [ebp+var_90]
0x1001ff97  movzx   edx, [ebp+arg_6]
0x1001ff9b  push    eax
0x1001ff9c  call    AppendCell
0x1001ffa1  mov     ecx, esi
0x1001ffa3  lea     eax, [ebp+var_90]
0x1001ffa9  nop     dword ptr [eax+00000000h]
0x1001ffb0  cmp     word ptr [eax], 0
0x1001ffb4  jz      short loc_1001FFBE
0x1001ffb6  add     eax, 2
0x1001ffb9  sub     ecx, 1
0x1001ffbc  jnz     short loc_1001FFB0
0x1001ffbe  mov     eax, esi
0x1001ffc0  mov     edi, ecx
0x1001ffc2  sub     eax, ecx
0x1001ffc4  neg     edi
0x1001ffc6  sbb     edi, edi
0x1001ffc8  and     edi, eax
0x1001ffca  test    ecx, ecx
0x1001ffcc  jz      short loc_1002000D
0x1001ffce  lea     ecx, [ebp+var_90]
0x1001ffd4  mov     eax, 7FFFFFFEh
0x1001ffd9  lea     ecx, [ecx+edi*2]
0x1001ffdc  mov     edx, offset asc_10005110; ":"
0x1001ffe1  sub     esi, edi
0x1001ffe3  jz      short loc_10020000
0x1001ffe5  test    eax, eax
0x1001ffe7  jz      short loc_10020000
0x1001ffe9  movzx   edi, word ptr [edx]
0x1001ffec  test    di, di
0x1001ffef  jz      short loc_10020000
0x1001fff1  mov     [ecx], di
0x1001fff4  add     edx, 2
0x1001fff7  add     ecx, 2
0x1001fffa  dec     eax
0x1001fffb  sub     esi, 1
0x1001fffe  jnz     short loc_1001FFE5
0x10020000  test    esi, esi
0x10020002  lea     eax, [ecx-2]
0x10020005  cmovnz  eax, ecx
0x10020008  xor     ecx, ecx
0x1002000a  mov     [eax], cx
0x1002000d  movzx   eax, [ebp+arg_8]
0x10020011  lea     ecx, [ebp+var_90]
0x10020017  movzx   edx, [ebp+arg_A]
0x1002001b  push    eax
0x1002001c  call    AppendCell
0x10020021  mov     ecx, [ebp+var_9C]; this
0x10020027  mov     [ebp+var_4], 0
0x1002002e  call    ?Names@ExcelWorkbook@@QAEPAVExcelNames@@XZ; ExcelWorkbook::Names(void)
0x10020033  push    1
0x10020035  mov     esi, eax
0x10020037  lea     eax, [ebp+var_90]
0x1002003d  push    eax
0x1002003e  push    dword ptr [ebp+var_98]
0x10020044  lea     eax, [ebp+var_98]
0x1002004a  mov     [ebp+var_94], esi
0x10020050  push    offset dword_1003A624; lpString
0x10020055  push    eax; LPSTR
0x10020056  movzx   eax, ?wInvokeMethod@@3GA; ushort wInvokeMethod
0x1002005d  push    0Bh; unsigned __int16
0x1002005f  push    eax; unsigned __int16
0x10020060  push    0B5h; int
0x10020065  push    esi; this
0x10020066  call    ?InvokeHelper@DispatchDriver@@QAAHJGGPAXPBEZZ; DispatchDriver::InvokeHelper(long,ushort,ushort,void *,uchar const *,...)
0x1002006b  add     esp, 24h
0x1002006e  jmp     short loc_1002007C
0x10020070  mov     eax, offset loc_10020076
0x10020075  retn
0x10020076  mov     esi, [ebp+var_94]
0x1002007c  test    esi, esi
0x1002007e  jz      short loc_10020092
0x10020080  mov     ecx, esi; this
0x10020082  call    ??1DispatchDriver@@QAE@XZ; DispatchDriver::~DispatchDriver(void)
0x10020087  push    8; unsigned int
0x10020089  push    esi; void *
0x1002008a  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1002008f  add     esp, 8
0x10020092  xor     eax, eax
0x10020094  mov     ecx, [ebp+var_C]
0x10020097  mov     large fs:0, ecx
0x1002009e  pop     ecx
0x1002009f  pop     edi
0x100200a0  pop     esi
0x100200a1  pop     ebx
0x100200a2  mov     ecx, [ebp+var_14]
0x100200a5  xor     ecx, ebp; StackCookie
0x100200a7  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100200ac  mov     esp, ebp
0x100200ae  pop     ebp
0x100200af  retn    10h
0x10036850  nop
0x10036851  nop
0x10036852  mov     edx, dword ptr [esp-4+arg_4]
0x10036856  lea     eax, [edx+0Ch]
0x10036859  mov     ecx, [edx-0A0h]
0x1003685f  xor     ecx, eax; StackCookie
0x10036861  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10036866  mov     ecx, [edx-8]
0x10036869  xor     ecx, eax; StackCookie
0x1003686b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10036870  mov     eax, offset stru_10036F90
0x10036875  jmp     ___CxxFrameHandler3
```
