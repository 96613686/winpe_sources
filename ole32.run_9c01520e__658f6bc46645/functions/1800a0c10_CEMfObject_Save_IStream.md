# CEMfObject::Save(IStream *)

- ea: `0x1800a0c10`
- end: `0x1800a0d60`
- name: `?Save@CEMfObject@@UEAAJPEAUIStream@@@Z`
- size: `336`
- prototype: `HRESULT __fastcall(CEMfObject *this, IStream *lpstream)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180046460`
- `0x1800a0c10`
- `0x1800a14a8`
- `0x1800ab940`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0c6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0c6b`
- `GDI32!DeleteDC` at `0x1800a0cb4`
- `GDI32!DeleteDC` at `0x1800a0cc2`
- `GDI32!DeleteDC` at `0x1800a0cb4`
- `GDI32!DeleteDC` at `0x1800a0cc2`
- `GDI32!CreateCompatibleDC` at `0x1800a0c57`
- `GDI32!CreateCompatibleDC` at `0x1800a0c57`
- `GDI32!GetWinMetaFileBits` at `0x1800a0c9f`
- `GDI32!GetWinMetaFileBits` at `0x1800a0c9f`

## pseudocode

```c
HRESULT __fastcall CEMfObject::Save(CEMfObject *this, IStream *lpstream)
{
  HENHMETAFILE__ **p_m_hPres; // rbx
  HDC hdcRef; // rax
  HDC v6; // rdi
  HRESULT result; // eax
  UINT WinMetaFileBits; // ebp
  int m_lWidth; // eax
  struct IStreamVtbl *lpVtbl; // rax
  unsigned int v11; // edx
  int v12; // r8d
  unsigned int dwBuf[4]; // [rsp+30h] [rbp-38h] BYREF

  p_m_hPres = &this->m_hPres;
  if ( ((unsigned int (__fastcall *)(CEMfObject *))this->lpVtbl[3].Release)(this) || !*p_m_hPres )
  {
    WinMetaFileBits = 0;
  }
  else
  {
    hdcRef = CreateCompatibleDC(0);
    v6 = hdcRef;
    if ( !hdcRef )
      goto LABEL_4;
    WinMetaFileBits = GetWinMetaFileBits(*p_m_hPres, 0, 0, 8, hdcRef);
    if ( !WinMetaFileBits )
    {
      DeleteDC(v6);
LABEL_4:
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    DeleteDC(v6);
  }
  m_lWidth = this->m_lWidth;
  dwBuf[0] = 0;
  dwBuf[1] = m_lWidth;
  dwBuf[2] = this->m_lHeight;
  lpVtbl = lpstream->lpVtbl;
  dwBuf[3] = WinMetaFileBits;
  result = ((__int64 (__fastcall *)(IStream *, unsigned int *, __int64))lpVtbl->Write)(lpstream, dwBuf, 16);
  if ( result >= 0 )
  {
    if ( ((unsigned int (__fastcall *)(CEMfObject *))this->lpVtbl[3].Release)(this) || !*p_m_hPres )
    {
      StSetSize(lpstream, v11, v12);
      return 0;
    }
    else
    {
      return UtHEMFToEMFStm(*p_m_hPres, WinMetaFileBits, lpstream, WRITE_AS_WMF);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800a0c10  mov     [rsp+arg_10], rbx
0x1800a0c15  mov     [rsp+arg_18], rbp
0x1800a0c1a  push    rsi
0x1800a0c1b  push    rdi
0x1800a0c1c  push    r14
0x1800a0c1e  sub     rsp, 50h
0x1800a0c22  mov     rax, cs:__security_cookie
0x1800a0c29  xor     rax, rsp
0x1800a0c2c  mov     [rsp+68h+var_28], rax
0x1800a0c31  mov     rax, [this]
0x1800a0c34  lea     rbx, [this+10h]
0x1800a0c38  mov     r14, lpstream
0x1800a0c3b  mov     rsi, this
0x1800a0c3e  mov     rax, [rax+58h]
0x1800a0c42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0c47  test    eax, eax
0x1800a0c49  jnz     loc_1800A0CD0
0x1800a0c4f  cmp     qword ptr [rbx], 0
0x1800a0c53  jz      short loc_1800A0CD0
0x1800a0c55  xor     ecx, ecx; hdc
0x1800a0c57  call    cs:__imp_CreateCompatibleDC
0x1800a0c5e  nop     dword ptr [rax+rax+00h]
0x1800a0c63  mov     rdi, rax
0x1800a0c66  test    rax, rax
0x1800a0c69  jnz     short loc_1800A0C8C
0x1800a0c6b  call    cs:__imp_GetLastError
0x1800a0c72  nop     dword ptr [rax+rax+00h]
0x1800a0c77  test    eax, eax
0x1800a0c79  jle     loc_1800A0D3D
0x1800a0c7f  movzx   eax, ax
0x1800a0c82  or      eax, 80070000h
0x1800a0c87  jmp     loc_1800A0D3D
0x1800a0c8c  mov     this, [rbx]; hemf
0x1800a0c8f  mov     r9d, 8; iMapMode
0x1800a0c95  xor     r8d, r8d; pData16
0x1800a0c98  mov     [rsp+68h+hdcRef], rdi; hdcRef
0x1800a0c9d  xor     edx, edx; cbData16
0x1800a0c9f  call    cs:__imp_GetWinMetaFileBits
0x1800a0ca6  nop     dword ptr [rax+rax+00h]
0x1800a0cab  mov     ebp, eax
0x1800a0cad  mov     this, rdi; hdc
0x1800a0cb0  test    eax, eax
0x1800a0cb2  jnz     short loc_1800A0CC2
0x1800a0cb4  call    cs:__imp_DeleteDC
0x1800a0cbb  nop     dword ptr [rax+rax+00h]
0x1800a0cc0  jmp     short loc_1800A0C6B
0x1800a0cc2  call    cs:__imp_DeleteDC
0x1800a0cc9  nop     dword ptr [rax+rax+00h]
0x1800a0cce  jmp     short loc_1800A0CD2
0x1800a0cd0  xor     ebp, ebp
0x1800a0cd2  mov     eax, [rsi+40h]
0x1800a0cd5  lea     lpstream, [rsp+68h+dwBuf]
0x1800a0cda  and     [rsp+68h+dwBuf], 0
0x1800a0cdf  xor     r9d, r9d
0x1800a0ce2  mov     [rsp+68h+dwBuf+4], eax
0x1800a0ce6  mov     this, r14
0x1800a0ce9  mov     eax, [rsi+44h]
0x1800a0cec  mov     [rsp+68h+dwBuf+8], eax
0x1800a0cf0  mov     rax, [r14]
0x1800a0cf3  lea     r8d, [r9+10h]
0x1800a0cf7  mov     [rsp+68h+dwBuf+0Ch], ebp
0x1800a0cfb  mov     rax, [rax+20h]
0x1800a0cff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0d04  test    eax, eax
0x1800a0d06  js      short loc_1800A0D3D
0x1800a0d08  mov     rax, [rsi]
0x1800a0d0b  mov     this, rsi
0x1800a0d0e  mov     rax, [rax+58h]
0x1800a0d12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0d17  test    eax, eax
0x1800a0d19  jnz     short loc_1800A0D33
0x1800a0d1b  mov     this, [rbx]; hEMF
0x1800a0d1e  test    this, this
0x1800a0d21  jz      short loc_1800A0D33
0x1800a0d23  lea     r9d, [rax+0Dh]; emfwType
0x1800a0d27  mov     r8, r14; lpstream
0x1800a0d2a  mov     edx, ebp; dwSize
0x1800a0d2c  call    ?UtHEMFToEMFStm@@YAJPEAUHENHMETAFILE__@@KPEAUIStream@@W4tagEMFWRITETYPE@@@Z; UtHEMFToEMFStm(HENHMETAFILE__ *,ulong,IStream *,tagEMFWRITETYPE)
0x1800a0d31  jmp     short loc_1800A0D3D
0x1800a0d33  mov     this, r14; pstm
0x1800a0d36  call    ?StSetSize@@YAJPEAUIStream@@KH@Z; StSetSize(IStream *,ulong,int)
0x1800a0d3b  xor     eax, eax
0x1800a0d3d  mov     this, [rsp+68h+var_28]
0x1800a0d42  xor     this, rsp; StackCookie
0x1800a0d45  call    __security_check_cookie
0x1800a0d4a  lea     r11, [rsp+68h+var_18]
0x1800a0d4f  mov     rbx, [r11+30h]
0x1800a0d53  mov     rbp, [r11+38h]
0x1800a0d57  mov     rsp, r11
0x1800a0d5a  pop     r14
0x1800a0d5c  pop     rdi
0x1800a0d5d  pop     rsi
0x1800a0d5e  retn
```
