# CMessageDlg::DoModalDialog(HINSTANCE__ *,ushort const *,ushort const *,ulong,ulong,ulong,char *)

- ea: `0x140001adc`
- end: `0x140001bea`
- name: `?DoModalDialog@CMessageDlg@@QEAA_JPEAUHINSTANCE__@@PEBG1KKKPEAD@Z`
- size: `270`
- prototype: `__int64 __fastcall(_QWORD *dwInitParam, HINSTANCE, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, UINT uID, char *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140001e74`

## callees

- `0x140001014`
- `0x1400019ec`
- `0x140001adc`
- `0x140001bf0`
- `0x140002168`
- `0x140002cb0`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x140001b64`
- `KERNEL32!FormatMessageW` at `0x140001b64`
- `KERNEL32!LocalFree` at `0x140001bb5`
- `KERNEL32!LocalFree` at `0x140001bb5`

## pseudocode

```c
__int64 __fastcall CMessageDlg::DoModalDialog(
        _QWORD *dwInitParam,
        HINSTANCE a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        unsigned int a6,
        UINT uID,
        char *a8)
{
  HWND v9; // rdx
  __int64 v10; // rax
  unsigned __int64 v11; // rbx
  unsigned __int16 *v12; // rax
  const unsigned __int16 *v13; // r8
  WCHAR Buffer[4]; // [rsp+40h] [rbp-238h] BYREF
  va_list Arguments; // [rsp+48h] [rbp-230h] BYREF
  unsigned __int16 Source[264]; // [rsp+50h] [rbp-228h] BYREF

  dwInitParam[3] = 32513;
  Arguments = a8;
  dwInitParam[2] = 0;
  LoadStr(uID, Source, 0x104u, &qword_1400044B0);
  *(_QWORD *)Buffer = 0;
  if ( FormatMessageW(0x500u, Source, 0, 0, Buffer, 0, &Arguments) )
  {
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)(*(_QWORD *)Buffer + 2 * v10) );
    v11 = (int)v10 + 1;
    v12 = (unsigned __int16 *)operator new(saturated_mul(v11, 2u));
    v13 = *(const unsigned __int16 **)Buffer;
    dwInitParam[4] = v12;
    StringCchCopyW(v12, v11, v13);
    LocalFree(*(HLOCAL *)Buffer);
  }
  return CDlg::_DoModalDlg((LPARAM)dwInitParam, v9, 107);
}

```

## disassembly

```asm
0x140001adc  mov     [rsp+arg_8], rbx
0x140001ae1  push    rdi
0x140001ae2  sub     rsp, 270h
0x140001ae9  mov     rax, cs:__security_cookie
0x140001af0  xor     rax, rsp
0x140001af3  mov     [rsp+278h+var_18], rax
0x140001afb  mov     rax, [rsp+278h+arg_38]
0x140001b03  lea     r9, qword_1400044B0; unsigned __int16 *
0x140001b0a  mov     rdi, rcx
0x140001b0d  mov     qword ptr [rcx+18h], 7F01h
0x140001b15  xor     ebx, ebx
0x140001b17  mov     [rsp+278h+var_230], rax
0x140001b1c  mov     [rcx+10h], rbx
0x140001b20  lea     rdx, [rsp+278h+Source]; unsigned __int16 *
0x140001b25  mov     ecx, [rsp+278h+uID]; uID
0x140001b2c  mov     r8d, 104h; unsigned int
0x140001b32  call    ?LoadStr@@YAJKPEAGKPEBG@Z; LoadStr(ulong,ushort *,ulong,ushort const *)
0x140001b37  lea     rax, [rsp+278h+var_230]
0x140001b3c  mov     qword ptr [rsp+278h+Buffer], rbx
0x140001b41  mov     [rsp+278h+Arguments], rax; Arguments
0x140001b46  lea     rdx, [rsp+278h+Source]; lpSource
0x140001b4b  lea     rax, [rsp+278h+Buffer]
0x140001b50  mov     [rsp+278h+nSize], ebx; nSize
0x140001b54  xor     r9d, r9d; dwLanguageId
0x140001b57  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140001b5c  xor     r8d, r8d; dwMessageId
0x140001b5f  mov     ecx, 500h; dwFlags
0x140001b64  call    cs:__imp_FormatMessageW
0x140001b6a  test    eax, eax
0x140001b6c  jz      short loc_140001BBB
0x140001b6e  mov     rcx, qword ptr [rsp+278h+Buffer]
0x140001b73  or      r8, 0FFFFFFFFFFFFFFFFh
0x140001b77  mov     rax, r8
0x140001b7a  inc     rax
0x140001b7d  cmp     [rcx+rax*2], bx
0x140001b81  jnz     short loc_140001B7A
0x140001b83  inc     eax
0x140001b85  movsxd  rbx, eax
0x140001b88  mov     eax, 2
0x140001b8d  mul     rbx
0x140001b90  cmovb   rax, r8
0x140001b94  mov     rcx, rax; Size
0x140001b97  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140001b9c  mov     r8, qword ptr [rsp+278h+Buffer]; unsigned __int16 *
0x140001ba1  mov     rdx, rbx; unsigned __int64
0x140001ba4  mov     rcx, rax; unsigned __int16 *
0x140001ba7  mov     [rdi+20h], rax
0x140001bab  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140001bb0  mov     rcx, qword ptr [rsp+278h+Buffer]; hMem
0x140001bb5  call    cs:__imp_LocalFree
0x140001bbb  mov     r8d, 6Bh ; 'k'; int
0x140001bc1  mov     rcx, rdi; dwInitParam
0x140001bc4  call    ?_DoModalDlg@CDlg@@IEAA_JPEAUHWND__@@H@Z; CDlg::_DoModalDlg(HWND__ *,int)
0x140001bc9  mov     rcx, [rsp+278h+var_18]
0x140001bd1  xor     rcx, rsp; StackCookie
0x140001bd4  call    __security_check_cookie
0x140001bd9  mov     rbx, [rsp+278h+arg_8]
0x140001be1  add     rsp, 270h
0x140001be8  pop     rdi
0x140001be9  retn
```
