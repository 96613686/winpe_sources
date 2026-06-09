# CMsftIsoImageManager::SetPathValidationFunction(ushort *)

- ea: `0x18002a7f0`
- end: `0x18002a8e5`
- name: `?SetPathValidationFunction@CMsftIsoImageManager@@EEAAJPEAG@Z`
- size: `245`
- prototype: `int(CMsftIsoImageManager *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18001f27c`
- `0x180028568`
- `0x180029138`
- `0x18002a7f0`
- `0x18002ade4`

## import_xrefs

- `SHLWAPI!SHCreateStreamOnFileW` at `0x18002a86a`
- `SHLWAPI!SHCreateStreamOnFileW` at `0x18002a86a`
- `OLEAUT32!__imp_SysStringLen` at `0x18002a811`
- `OLEAUT32!__imp_SysStringLen` at `0x18002a811`

## pseudocode

```c
__int64 __fastcall CMsftIsoImageManager::SetPathValidationFunction(struct IUnknown **this, unsigned __int16 *a2)
{
  UINT v4; // eax
  HRESULT v5; // ebx
  IStream *ppstm; // [rsp+50h] [rbp+18h] BYREF

  ppstm = 0;
  v4 = SysStringLen(a2);
  if ( v4 <= 0x104 )
  {
    v5 = 0;
    if ( v4 && (v5 = SHCreateStreamOnFileW(a2, 0x20u, &ppstm), v5 < 0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 3u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          11,
          (unsigned int)&WPP_d3f050a05e0c3b0048cc767be3a359fd_Traceguids,
          (_DWORD)a2,
          v5);
      }
    }
    else if ( this[17] != (struct IUnknown *)ppstm )
    {
      ATL::AtlComPtrAssign(this + 17, (struct IUnknown *)ppstm);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, &WPP_d3f050a05e0c3b0048cc767be3a359fd_Traceguids);
    }
    v5 = -2147024809;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppstm);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002a7f0  mov     [rsp+arg_0], rbx
0x18002a7f5  mov     [rsp+arg_8], rsi
0x18002a7fa  push    rdi
0x18002a7fb  sub     rsp, 30h
0x18002a7ff  mov     rsi, rcx
0x18002a802  mov     [rsp+38h+ppstm], 0
0x18002a80b  mov     rcx, rdx; pbstr
0x18002a80e  mov     rdi, rdx
0x18002a811  call    cs:__imp_SysStringLen
0x18002a817  cmp     eax, 104h
0x18002a81c  jbe     short loc_18002A859
0x18002a81e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a825  lea     rax, WPP_GLOBAL_Control
0x18002a82c  cmp     rcx, rax
0x18002a82f  jz      short loc_18002A852
0x18002a831  test    byte ptr [rcx+44h], 4
0x18002a835  jz      short loc_18002A852
0x18002a837  cmp     byte ptr [rcx+41h], 3
0x18002a83b  jb      short loc_18002A852
0x18002a83d  mov     rcx, [rcx+38h]
0x18002a841  lea     r8, WPP_d3f050a05e0c3b0048cc767be3a359fd_Traceguids
0x18002a848  mov     edx, 0Ah
0x18002a84d  call    WPP_SF_
0x18002a852  mov     ebx, 80070057h
0x18002a857  jmp     short loc_18002A8C9
0x18002a859  xor     ebx, ebx
0x18002a85b  test    eax, eax
0x18002a85d  jz      short loc_18002A8B3
0x18002a85f  lea     r8, [rsp+38h+ppstm]; ppstm
0x18002a864  mov     rcx, rdi; pszFile
0x18002a867  lea     edx, [rbx+20h]; grfMode
0x18002a86a  call    cs:__imp_SHCreateStreamOnFileW
0x18002a870  mov     ebx, eax
0x18002a872  test    eax, eax
0x18002a874  jns     short loc_18002A8B3
0x18002a876  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a87d  lea     rax, WPP_GLOBAL_Control
0x18002a884  cmp     rcx, rax
0x18002a887  jz      short loc_18002A8C9
0x18002a889  test    byte ptr [rcx+44h], 4
0x18002a88d  jz      short loc_18002A8C9
0x18002a88f  cmp     byte ptr [rcx+41h], 3
0x18002a893  jb      short loc_18002A8C9
0x18002a895  mov     rcx, [rcx+38h]
0x18002a899  lea     r8, WPP_d3f050a05e0c3b0048cc767be3a359fd_Traceguids
0x18002a8a0  mov     edx, 0Bh
0x18002a8a5  mov     [rsp+38h+var_18], ebx
0x18002a8a9  mov     r9, rdi
0x18002a8ac  call    WPP_SF_Sd
0x18002a8b1  jmp     short loc_18002A8C9
0x18002a8b3  mov     rdx, [rsp+38h+ppstm]; struct IUnknown *
0x18002a8b8  lea     rcx, [rsi+88h]; struct IUnknown **
0x18002a8bf  cmp     [rcx], rdx
0x18002a8c2  jz      short loc_18002A8C9
0x18002a8c4  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18002a8c9  lea     rcx, [rsp+38h+ppstm]
0x18002a8ce  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002a8d3  mov     rsi, [rsp+38h+arg_8]
0x18002a8d8  mov     eax, ebx
0x18002a8da  mov     rbx, [rsp+38h+arg_0]
0x18002a8df  add     rsp, 30h
0x18002a8e3  pop     rdi
0x18002a8e4  retn
```
