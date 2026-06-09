# PsIsMyFileType(ushort *,_GUID *)

- ea: `0x180004bc0`
- end: `0x180004c97`
- name: `?PsIsMyFileType@@YAHPEAGPEAU_GUID@@@Z`
- size: `215`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct _GUID *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180004bc0`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180004be9`
- `msvcrt!wcsrchr` at `0x180004be9`
- `msvcrt!_wcsicmp` at `0x180004c5f`
- `msvcrt!_wcsicmp` at `0x180004c5f`
- `KERNEL32!SetLastError` at `0x180004c84`
- `KERNEL32!SetLastError` at `0x180004c84`

## string_xrefs

- `0x180004c0b`: `ps1xml`
- `0x180004c3e`: `cdxml`

## pseudocode

```c
__int64 __fastcall PsIsMyFileType(unsigned __int16 *a1, struct _GUID *a2)
{
  unsigned int v3; // ebx
  wchar_t *v4; // rbp
  __int64 v5; // rdi
  wchar_t *String2[13]; // [rsp+20h] [rbp-68h]

  if ( a2 && (*a2 = 0, a1) )
  {
    v3 = 0;
    v4 = wcsrchr(a1, 0x2Eu);
    if ( v4 )
    {
      v5 = 0;
      String2[0] = L"ps1";
      String2[1] = L"ps1xml";
      String2[2] = L"psc1";
      String2[3] = L"psd1";
      v3 = 1;
      String2[4] = L"psm1";
      String2[5] = L"cdxml";
      String2[6] = L"mof";
      while ( _wcsicmp(v4 + 1, String2[v5]) )
      {
        v5 = (unsigned int)(v5 + 1);
        if ( (int)v5 >= 7 )
          return 0;
      }
      *a2 = guidPsSip;
    }
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
  return v3;
}

```

## disassembly

```asm
0x180004bc0  push    rbx
0x180004bc2  push    rbp
0x180004bc3  push    rsi
0x180004bc4  push    rdi
0x180004bc5  sub     rsp, 68h
0x180004bc9  mov     rsi, rdx
0x180004bcc  test    rdx, rdx
0x180004bcf  jz      loc_180004C7F
0x180004bd5  xorps   xmm0, xmm0
0x180004bd8  movups  xmmword ptr [rdx], xmm0
0x180004bdb  test    rcx, rcx
0x180004bde  jz      loc_180004C7F
0x180004be4  mov     edx, 2Eh ; '.'; Ch
0x180004be9  call    cs:__imp_wcsrchr
0x180004bef  xor     ebx, ebx
0x180004bf1  mov     rbp, rax
0x180004bf4  test    rax, rax
0x180004bf7  jz      loc_180004C8C
0x180004bfd  lea     rax, aPs1; "ps1"
0x180004c04  xor     edi, edi
0x180004c06  mov     [rsp+88h+String2], rax
0x180004c0b  lea     rax, aPs1xml; "ps1xml"
0x180004c12  mov     [rsp+88h+var_60], rax
0x180004c17  lea     rax, aPsc1; "psc1"
0x180004c1e  mov     [rsp+88h+var_58], rax
0x180004c23  lea     rax, aPsd1; "psd1"
0x180004c2a  mov     [rsp+88h+var_50], rax
0x180004c2f  lea     ebx, [rdi+1]
0x180004c32  lea     rax, aPsm1; "psm1"
0x180004c39  mov     [rsp+88h+var_48], rax
0x180004c3e  lea     rax, aCdxml; "cdxml"
0x180004c45  mov     [rsp+88h+var_40], rax
0x180004c4a  lea     rax, aMof; "mof"
0x180004c51  mov     [rsp+88h+var_38], rax
0x180004c56  mov     rdx, [rsp+rdi*8+88h+String2]; String2
0x180004c5b  lea     rcx, [rbp+2]; String1
0x180004c5f  call    cs:__imp__wcsicmp
0x180004c65  test    eax, eax
0x180004c67  jz      short loc_180004C72
0x180004c69  add     edi, ebx
0x180004c6b  cmp     edi, 7
0x180004c6e  jl      short loc_180004C56
0x180004c70  jmp     short loc_180004C8A
0x180004c72  movups  xmm0, xmmword ptr cs:guidPsSip.Data1
0x180004c79  movdqu  xmmword ptr [rsi], xmm0
0x180004c7d  jmp     short loc_180004C8C
0x180004c7f  mov     ecx, 57h ; 'W'; dwErrCode
0x180004c84  call    cs:__imp_SetLastError
0x180004c8a  xor     ebx, ebx
0x180004c8c  mov     eax, ebx
0x180004c8e  add     rsp, 68h
0x180004c92  pop     rdi
0x180004c93  pop     rsi
0x180004c94  pop     rbp
0x180004c95  pop     rbx
0x180004c96  retn
```
