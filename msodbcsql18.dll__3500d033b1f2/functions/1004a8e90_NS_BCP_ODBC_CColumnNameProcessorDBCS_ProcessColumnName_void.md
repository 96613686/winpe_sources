# NS_BCP_ODBC::CColumnNameProcessorDBCS::ProcessColumnName(void)

- ea: `0x1004a8e90`
- end: `0x1004a9014`
- name: `?ProcessColumnName@CColumnNameProcessorDBCS@NS_BCP_ODBC@@UEAAFXZ`
- size: `388`
- prototype: `__int16 __fastcall(NS_BCP_ODBC::CColumnNameProcessorDBCS *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x100412efc`
- `0x1004a8e90`
- `0x1004af970`
- `0x1005212b4`
- `0x100546a7c`

## import_xrefs

- `KERNEL32!IsDBCSLeadByteEx` at `0x1004a8ee2`
- `KERNEL32!IsDBCSLeadByteEx` at `0x1004a8ee2`
- `KERNEL32!SetFilePointer` at `0x1004a8f84`
- `KERNEL32!SetFilePointer` at `0x1004a8f84`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x1004a8f35`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x1004a8f35`

## pseudocode

```c
__int64 __fastcall NS_BCP_ODBC::CColumnNameProcessorDBCS::ProcessColumnName(
        NS_BCP_ODBC::CColumnNameProcessorDBCS *this)
{
  unsigned __int16 v1; // bx
  unsigned __int8 *v2; // r14
  unsigned int v4; // esi
  __int64 v5; // rdx
  __int64 v6; // rcx

  v1 = 0;
  v2 = (unsigned __int8 *)this + 40;
  *((_DWORD *)this + 3) = 0;
  while ( 1 )
  {
    if ( (unsigned __int16)bcpRead(*((struct tagDBC **)this + 2), *((struct BCPFILE **)this + 3), 1u, v2) )
    {
      v1 = -1;
      if ( (bidGblFlags & 2) == 0 )
        return v1;
      v5 = 1240073;
      goto LABEL_23;
    }
    v4 = 1;
    if ( IsDBCSLeadByteEx(*((_DWORD *)this + 8), *v2) )
    {
      if ( (unsigned __int16)bcpRead(
                               *((struct tagDBC **)this + 2),
                               *((struct BCPFILE **)this + 3),
                               1u,
                               (unsigned __int8 *)this + 41) )
      {
        v1 = -1;
        if ( (bidGblFlags & 2) == 0 )
          return v1;
        v5 = 1248265;
LABEL_23:
        bidTraceMark(0, v5);
        goto LABEL_24;
      }
      v4 = 2;
    }
    if ( !SystemLocale::FastAsciiMultiByteToWideChar(*((_DWORD *)this + 8), (LPCCH)v2, v4, (LPWSTR)this + 4, 1u, 0, 0) )
    {
      v1 = -1;
      if ( (bidGblFlags & 2) == 0 )
        return v1;
      v5 = 1260553;
      goto LABEL_23;
    }
    if ( iswspace(*((_WORD *)this + 4)) )
      break;
    if ( (int)++*((_DWORD *)this + 3) > 129 )
      goto LABEL_15;
  }
  v6 = *((_QWORD *)this + 3);
  if ( *(_DWORD *)(v6 + 64) )
    *(_QWORD *)(v6 + 56) -= v4;
  else
    SetFilePointer(*(HANDLE *)v6, -v4, 0, 1u);
LABEL_15:
  if ( !*((_DWORD *)this + 3) || *((int *)this + 3) > 129 )
  {
    v1 = -1;
    if ( (bidGblFlags & 2) == 0 )
      return v1;
    v5 = 1276937;
    goto LABEL_23;
  }
LABEL_24:
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned __int16)_bidx_SNACOdbc_ErrCode(0, 0x138809u, v1);
  return v1;
}

```

## disassembly

```asm
0x1004a8e90  mov     rax, rsp
0x1004a8e93  mov     [rax+8], rbx
0x1004a8e97  mov     [rax+10h], rbp
0x1004a8e9b  mov     [rax+18h], rsi
0x1004a8e9f  mov     [rax+20h], rdi
0x1004a8ea3  push    r13
0x1004a8ea5  push    r14
0x1004a8ea7  push    r15
0x1004a8ea9  sub     rsp, 40h
0x1004a8ead  xor     ebx, ebx
0x1004a8eaf  lea     r14, [rcx+28h]
0x1004a8eb3  mov     rdi, rcx
0x1004a8eb6  mov     [rcx+0Ch], ebx
0x1004a8eb9  lea     r13d, [rbx+1]
0x1004a8ebd  mov     rdx, [rdi+18h]; struct BCPFILE *
0x1004a8ec1  mov     r9, r14; unsigned __int8 *
0x1004a8ec4  mov     rcx, [rdi+10h]; struct tagDBC *
0x1004a8ec8  mov     r8d, r13d; unsigned int
0x1004a8ecb  call    ?bcpRead@@YAFPEAUtagDBC@@PEAUBCPFILE@@IPEAE@Z; bcpRead(tagDBC *,BCPFILE *,uint,uchar *)
0x1004a8ed0  cmp     bx, ax
0x1004a8ed3  jnz     loc_1004A8FBE
0x1004a8ed9  mov     dl, [r14]; TestChar
0x1004a8edc  mov     esi, r13d
0x1004a8edf  mov     ecx, [rdi+20h]; CodePage
0x1004a8ee2  call    cs:__imp_IsDBCSLeadByteEx
0x1004a8ee8  test    eax, eax
0x1004a8eea  jz      short loc_1004A8F0A
0x1004a8eec  mov     rdx, [rdi+18h]; struct BCPFILE *
0x1004a8ef0  lea     r9, [rdi+29h]; unsigned __int8 *
0x1004a8ef4  mov     rcx, [rdi+10h]; struct tagDBC *
0x1004a8ef8  mov     r8d, r13d; unsigned int
0x1004a8efb  call    ?bcpRead@@YAFPEAUtagDBC@@PEAUBCPFILE@@IPEAE@Z; bcpRead(tagDBC *,BCPFILE *,uint,uchar *)
0x1004a8f00  cmp     bx, ax
0x1004a8f03  jnz     short loc_1004A8F51
0x1004a8f05  mov     esi, 2
0x1004a8f0a  mov     ecx, [rdi+20h]; CodePage
0x1004a8f0d  lea     r9, [rdi+8]; lpWideCharStr
0x1004a8f11  mov     [rsp+58h+var_28], bl; bool
0x1004a8f15  mov     rdx, r14; lpMultiByteStr
0x1004a8f18  mov     [rsp+58h+var_30], rbx; unsigned int *
0x1004a8f1d  mov     r8d, esi; cbMultiByte
0x1004a8f20  mov     [rsp+58h+var_38], r13; unsigned __int64
0x1004a8f25  mov     ebp, esi
0x1004a8f27  call    ?FastAsciiMultiByteToWideChar@SystemLocale@@CA_KIPEBD_JPEAG_KPEAK_N@Z; SystemLocale::FastAsciiMultiByteToWideChar(uint,char const *,__int64,ushort *,unsigned __int64,ulong *,bool)
0x1004a8f2c  test    rax, rax
0x1004a8f2f  jz      short loc_1004A8FAB
0x1004a8f31  movzx   ecx, word ptr [rdi+8]; C
0x1004a8f35  call    cs:__imp_iswspace
0x1004a8f3b  test    eax, eax
0x1004a8f3d  jnz     short loc_1004A8F68
0x1004a8f3f  add     [rdi+0Ch], r13d
0x1004a8f43  cmp     dword ptr [rdi+0Ch], 81h
0x1004a8f4a  jg      short loc_1004A8F8A
0x1004a8f4c  jmp     loc_1004A8EBD
0x1004a8f51  or      ebx, 0FFFFFFFFh
0x1004a8f54  test    byte ptr cs:_bidGblFlags, 2
0x1004a8f5b  jz      loc_1004A8FF2
0x1004a8f61  mov     edx, 130C09h
0x1004a8f66  jmp     short loc_1004A8FCF
0x1004a8f68  mov     rcx, [rdi+18h]
0x1004a8f6c  cmp     [rcx+40h], ebx
0x1004a8f6f  jz      short loc_1004A8F77
0x1004a8f71  sub     [rcx+38h], rbp
0x1004a8f75  jmp     short loc_1004A8F8A
0x1004a8f77  mov     rcx, [rcx]; hFile
0x1004a8f7a  neg     esi
0x1004a8f7c  mov     edx, esi; lDistanceToMove
0x1004a8f7e  mov     r9d, r13d; dwMoveMethod
0x1004a8f81  xor     r8d, r8d; lpDistanceToMoveHigh
0x1004a8f84  call    cs:__imp_SetFilePointer
0x1004a8f8a  cmp     [rdi+0Ch], ebx
0x1004a8f8d  jz      short loc_1004A8F98
0x1004a8f8f  cmp     dword ptr [rdi+0Ch], 81h
0x1004a8f96  jle     short loc_1004A8FD6
0x1004a8f98  or      ebx, 0FFFFFFFFh
0x1004a8f9b  test    byte ptr cs:_bidGblFlags, 2
0x1004a8fa2  jz      short loc_1004A8FF2
0x1004a8fa4  mov     edx, 137C09h
0x1004a8fa9  jmp     short loc_1004A8FCF
0x1004a8fab  or      ebx, 0FFFFFFFFh
0x1004a8fae  test    byte ptr cs:_bidGblFlags, 2
0x1004a8fb5  jz      short loc_1004A8FF2
0x1004a8fb7  mov     edx, 133C09h
0x1004a8fbc  jmp     short loc_1004A8FCF
0x1004a8fbe  or      ebx, 0FFFFFFFFh
0x1004a8fc1  test    byte ptr cs:_bidGblFlags, 2
0x1004a8fc8  jz      short loc_1004A8FF2
0x1004a8fca  mov     edx, 12EC09h
0x1004a8fcf  xor     ecx, ecx
0x1004a8fd1  call    _bidTraceMark
0x1004a8fd6  test    byte ptr cs:_bidGblFlags, 2
0x1004a8fdd  jz      short loc_1004A8FF2
0x1004a8fdf  movzx   r8d, bx; __int16
0x1004a8fe3  mov     edx, 138809h; unsigned __int64
0x1004a8fe8  xor     ecx, ecx; unsigned __int64
0x1004a8fea  call    ?_bidx_SNACOdbc_ErrCode@@YAF_K0F@Z; _bidx_SNACOdbc_ErrCode(unsigned __int64,unsigned __int64,short)
0x1004a8fef  movzx   ebx, ax
0x1004a8ff2  mov     rbp, [rsp+58h+arg_8]
0x1004a8ff7  movzx   eax, bx
0x1004a8ffa  mov     rbx, [rsp+58h+arg_0]
0x1004a8fff  mov     rsi, [rsp+58h+arg_10]
0x1004a9004  mov     rdi, [rsp+58h+arg_18]
0x1004a9009  add     rsp, 40h
0x1004a900d  pop     r15
0x1004a900f  pop     r14
0x1004a9011  pop     r13
0x1004a9013  retn
```
