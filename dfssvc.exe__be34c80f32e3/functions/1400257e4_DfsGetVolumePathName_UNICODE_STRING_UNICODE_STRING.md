# DfsGetVolumePathName(_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x1400257e4`
- end: `0x14002598c`
- name: `?DfsGetVolumePathName@@YAKPEAU_UNICODE_STRING@@0@Z`
- size: `424`
- prototype: `unsigned int __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x140024c7c`

## callees

- `0x1400011c4`
- `0x1400011d0`
- `0x140005a94`
- `0x140005ad8`
- `0x1400096ac`
- `0x1400257e4`
- `0x1400586a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025888`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025888`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x14002586a`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x14002586a`

## pseudocode

```c
__int64 __fastcall DfsGetVolumePathName(struct _UNICODE_STRING *a1, struct _UNICODE_STRING *a2)
{
  PWSTR Buffer; // rdi
  DWORD LastError; // ebx
  DWORD v5; // r14d
  WCHAR *v6; // rax
  WCHAR *v7; // rsi
  _UNKNOWN **v8; // rax
  unsigned int *v9; // rcx

  Buffer = a1->Buffer;
  LastError = 0;
  v5 = 260;
  if ( a1->Length >= 0xAu && *Buffer == 92 && Buffer[1] == 63 && Buffer[2] == 63 && Buffer[3] == 92 )
    Buffer += 4;
  while ( 1 )
  {
    v6 = (WCHAR *)operator new(saturated_mul(v5, 2u));
    v7 = v6;
    if ( !v6 )
      return 8;
    if ( GetVolumePathNameW(Buffer, v6, v5) )
      break;
    operator delete(v7);
    v7 = 0;
    LastError = GetLastError();
    v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
    v9 = pWppControl;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x20) != 0
      && *((_BYTE *)pWppControl + 25) >= 2u )
    {
      WPP_SF_dD(*((_QWORD *)pWppControl + 2), 13, WPP_06cdb52cbe4531ba727f9e22c79a690d_Traceguids, LastError, v5);
      v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
      v9 = pWppControl;
    }
    if ( LastError != 111 )
    {
      if ( v8 != &WPP_GLOBAL_Control && v9 && (v9[7] & 0x20) != 0 && *((_BYTE *)v9 + 25) >= 2u )
        WPP_SF_(*((_QWORD *)v9 + 2), 15, WPP_06cdb52cbe4531ba727f9e22c79a690d_Traceguids);
      break;
    }
    if ( v8 != &WPP_GLOBAL_Control && v9 && (v9[7] & 0x20) != 0 && *((_BYTE *)v9 + 25) >= 2u )
      WPP_SF_D(*((_QWORD *)v9 + 2), 14, WPP_06cdb52cbe4531ba727f9e22c79a690d_Traceguids, v5);
    v5 *= 2;
  }
  if ( LastError || (LastError = DfsRtlInitUnicodeStringEx(a2, v7)) != 0 )
  {
    if ( v7 )
      operator delete(v7);
  }
  return LastError;
}

```

## disassembly

```asm
0x1400257e4  mov     [rsp+arg_0], rbx
0x1400257e9  mov     [rsp+arg_8], rbp
0x1400257ee  mov     [rsp+arg_10], rsi
0x1400257f3  push    rdi
0x1400257f4  push    r13
0x1400257f6  push    r14
0x1400257f8  sub     rsp, 30h
0x1400257fc  mov     rdi, [rcx+8]
0x140025800  xor     ebx, ebx
0x140025802  cmp     word ptr [rcx], 0Ah
0x140025806  mov     rbp, rdx
0x140025809  mov     r14d, 104h
0x14002580f  jb      short loc_140025830
0x140025811  cmp     word ptr [rdi], 5Ch ; '\'
0x140025815  jnz     short loc_140025830
0x140025817  cmp     word ptr [rdi+2], 3Fh ; '?'
0x14002581c  jnz     short loc_140025830
0x14002581e  cmp     word ptr [rdi+4], 3Fh ; '?'
0x140025823  jnz     short loc_140025830
0x140025825  cmp     word ptr [rdi+6], 5Ch ; '\'
0x14002582a  jnz     short loc_140025830
0x14002582c  add     rdi, 8
0x140025830  lea     r13, WPP_GLOBAL_Control
0x140025837  mov     ecx, r14d
0x14002583a  mov     eax, 2
0x14002583f  mul     rcx
0x140025842  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140025849  cmovo   rax, rcx
0x14002584d  mov     rcx, rax; Size
0x140025850  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140025855  mov     rsi, rax
0x140025858  test    rax, rax
0x14002585b  jz      loc_14002596B
0x140025861  mov     r8d, r14d; cchBufferLength
0x140025864  mov     rdx, rax; lpszVolumePathName
0x140025867  mov     rcx, rdi; lpszFileName
0x14002586a  call    cs:__imp_GetVolumePathNameW
0x140025871  nop     dword ptr [rax+rax+00h]
0x140025876  test    eax, eax
0x140025878  jnz     loc_140025947
0x14002587e  mov     rcx, rsi; Block
0x140025881  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140025886  xor     esi, esi
0x140025888  call    cs:__imp_GetLastError
0x14002588f  nop     dword ptr [rax+rax+00h]
0x140025894  mov     ebx, eax
0x140025896  mov     rax, cs:WPP_GLOBAL_Control
0x14002589d  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400258a4  cmp     rax, r13
0x1400258a7  jz      short loc_1400258E3
0x1400258a9  test    rcx, rcx
0x1400258ac  jz      short loc_1400258E3
0x1400258ae  test    byte ptr [rcx+1Ch], 20h
0x1400258b2  jz      short loc_1400258E3
0x1400258b4  cmp     byte ptr [rcx+19h], 2
0x1400258b8  jb      short loc_1400258E3
0x1400258ba  mov     rcx, [rcx+10h]
0x1400258be  lea     edx, [rsi+0Dh]
0x1400258c1  mov     r9d, ebx
0x1400258c4  mov     [rsp+48h+var_28], r14d
0x1400258c9  lea     r8, WPP_06cdb52cbe4531ba727f9e22c79a690d_Traceguids
0x1400258d0  call    WPP_SF_dD
0x1400258d5  mov     rax, cs:WPP_GLOBAL_Control
0x1400258dc  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400258e3  cmp     ebx, 6Fh ; 'o'
0x1400258e6  jnz     short loc_14002591C
0x1400258e8  cmp     rax, r13
0x1400258eb  jz      short loc_140025914
0x1400258ed  test    rcx, rcx
0x1400258f0  jz      short loc_140025914
0x1400258f2  test    byte ptr [rcx+1Ch], 20h
0x1400258f6  jz      short loc_140025914
0x1400258f8  cmp     byte ptr [rcx+19h], 2
0x1400258fc  jb      short loc_140025914
0x1400258fe  mov     rcx, [rcx+10h]
0x140025902  lea     edx, [rbx-61h]
0x140025905  mov     r9d, r14d
0x140025908  lea     r8, WPP_06cdb52cbe4531ba727f9e22c79a690d_Traceguids
0x14002590f  call    WPP_SF_D
0x140025914  add     r14d, r14d
0x140025917  jmp     loc_140025837
0x14002591c  cmp     rax, r13
0x14002591f  jz      short loc_140025947
0x140025921  test    rcx, rcx
0x140025924  jz      short loc_140025947
0x140025926  test    byte ptr [rcx+1Ch], 20h
0x14002592a  jz      short loc_140025947
0x14002592c  cmp     byte ptr [rcx+19h], 2
0x140025930  jb      short loc_140025947
0x140025932  mov     rcx, [rcx+10h]
0x140025936  lea     r8, WPP_06cdb52cbe4531ba727f9e22c79a690d_Traceguids
0x14002593d  mov     edx, 0Fh
0x140025942  call    WPP_SF_
0x140025947  test    ebx, ebx
0x140025949  jnz     short loc_14002595C
0x14002594b  mov     rdx, rsi
0x14002594e  mov     rcx, rbp
0x140025951  call    DfsRtlInitUnicodeStringEx
0x140025956  mov     ebx, eax
0x140025958  test    eax, eax
0x14002595a  jz      short loc_140025970
0x14002595c  test    rsi, rsi
0x14002595f  jz      short loc_140025970
0x140025961  mov     rcx, rsi; Block
0x140025964  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140025969  jmp     short loc_140025970
0x14002596b  mov     ebx, 8
0x140025970  mov     rbp, [rsp+48h+arg_8]
0x140025975  mov     eax, ebx
0x140025977  mov     rbx, [rsp+48h+arg_0]
0x14002597c  mov     rsi, [rsp+48h+arg_10]
0x140025981  add     rsp, 30h
0x140025985  pop     r14
0x140025987  pop     r13
0x140025989  pop     rdi
0x14002598a  retn
```
