# OUTPUT_ENTRY::UpdateEncodingsRejectedIfNeeded(char const *)

- ea: `0x1800089f0`
- end: `0x180008b08`
- name: `?UpdateEncodingsRejectedIfNeeded@OUTPUT_ENTRY@@QEAAXPEBD@Z`
- size: `280`
- prototype: `void __fastcall(OUTPUT_ENTRY *this, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180004220`

## callees

- `0x1800088d8`
- `0x1800089f0`
- `0x180008bf0`

## import_xrefs

- `iisutil!?FindString@MULTISZA@@QEAAHPEBD@Z` at `0x180008a63`
- `iisutil!?FindString@MULTISZA@@QEAAHPEBD@Z` at `0x180008aab`
- `iisutil!?FindString@MULTISZA@@QEAAHPEBD@Z` at `0x180008a63`
- `iisutil!?FindString@MULTISZA@@QEAAHPEBD@Z` at `0x180008aab`
- `iisutil!?First@MULTISZA@@QEBAPEBDXZ` at `0x180008a48`
- `iisutil!?First@MULTISZA@@QEBAPEBDXZ` at `0x180008a9d`
- `iisutil!?First@MULTISZA@@QEBAPEBDXZ` at `0x180008a48`
- `iisutil!?First@MULTISZA@@QEBAPEBDXZ` at `0x180008a9d`
- `iisutil!?Append@MULTISZA@@QEAAHPEBD@Z` at `0x180008abb`
- `iisutil!?Append@MULTISZA@@QEAAHPEBD@Z` at `0x180008abb`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180008a3d`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180008a3d`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180008a85`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180008a85`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180008a92`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180008a92`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180008ada`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180008ada`
- `iisutil!??1MULTISZA@@QEAA@XZ` at `0x180008ae5`
- `iisutil!??1MULTISZA@@QEAA@XZ` at `0x180008ae5`
- `iisutil!??0MULTISZA@@QEAA@XZ` at `0x180008a16`
- `iisutil!??0MULTISZA@@QEAA@XZ` at `0x180008a16`
- `iisutil!?Next@MULTISZA@@QEBAPEBDPEBD@Z` at `0x180008a75`
- `iisutil!?Next@MULTISZA@@QEBAPEBDPEBD@Z` at `0x180008ac9`
- `iisutil!?Next@MULTISZA@@QEBAPEBDPEBD@Z` at `0x180008a75`
- `iisutil!?Next@MULTISZA@@QEBAPEBDPEBD@Z` at `0x180008ac9`

## pseudocode

```c
void __fastcall OUTPUT_ENTRY::UpdateEncodingsRejectedIfNeeded(OUTPUT_ENTRY *this, const char *a2)
{
  CReaderWriterLock3 *v4; // rdi
  int v5; // esi
  const char *v6; // rax
  MULTISZA *v7; // rbp
  const char *v8; // rbx
  const char *i; // rax
  const char *v10; // rbx
  _BYTE v11[56]; // [rsp+20h] [rbp-58h] BYREF

  MULTISZA::MULTISZA((MULTISZA *)v11);
  if ( (int)ParseAcceptEncoding(a2, (struct MULTISZA *)v11) >= 0 )
  {
    v4 = (OUTPUT_ENTRY *)((char *)this + 816);
    v5 = 0;
    CReaderWriterLock3::ReadLock((OUTPUT_ENTRY *)((char *)this + 816));
    v6 = MULTISZA::First((MULTISZA *)v11);
    v7 = (OUTPUT_ENTRY *)((char *)this + 896);
    while ( 1 )
    {
      v8 = v6;
      if ( !v6 )
        break;
      if ( !MULTISZA::FindString(v7, v6) )
      {
        v5 = 1;
        break;
      }
      v6 = MULTISZA::Next((MULTISZA *)v11, v8);
    }
    CReaderWriterLock3::ReadUnlock(v4);
    if ( v5 )
    {
      CReaderWriterLock3::WriteLock(v4);
      for ( i = MULTISZA::First((MULTISZA *)v11); ; i = MULTISZA::Next((MULTISZA *)v11, v10) )
      {
        v10 = i;
        if ( !i )
          break;
        if ( !MULTISZA::FindString(v7, i) )
          MULTISZA::Append(v7, v10);
      }
      CReaderWriterLock3::WriteUnlock(v4);
    }
  }
  MULTISZA::~MULTISZA((MULTISZA *)v11);
}

```

## disassembly

```asm
0x1800089f0  mov     [rsp+arg_10], rbx
0x1800089f5  push    rbp
0x1800089f6  push    rsi
0x1800089f7  push    rdi
0x1800089f8  sub     rsp, 60h
0x1800089fc  mov     rax, cs:__security_cookie
0x180008a03  xor     rax, rsp
0x180008a06  mov     [rsp+78h+var_20], rax
0x180008a0b  mov     rbp, rcx
0x180008a0e  mov     rbx, rdx
0x180008a11  lea     rcx, [rsp+78h+var_58]
0x180008a16  call    cs:__imp_??0MULTISZA@@QEAA@XZ; MULTISZA::MULTISZA(void)
0x180008a1c  lea     rdx, [rsp+78h+var_58]; struct MULTISZA *
0x180008a21  mov     rcx, rbx; char *
0x180008a24  call    ?ParseAcceptEncoding@@YAJPEBDPEAVMULTISZA@@@Z; ParseAcceptEncoding(char const *,MULTISZA *)
0x180008a29  test    eax, eax
0x180008a2b  js      loc_180008AE0
0x180008a31  lea     rdi, [rbp+330h]
0x180008a38  xor     esi, esi
0x180008a3a  mov     rcx, rdi
0x180008a3d  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180008a43  lea     rcx, [rsp+78h+var_58]
0x180008a48  call    cs:__imp_?First@MULTISZA@@QEBAPEBDXZ; MULTISZA::First(void)
0x180008a4e  add     rbp, 380h
0x180008a55  mov     rbx, rax
0x180008a58  test    rax, rax
0x180008a5b  jz      short loc_180008A82
0x180008a5d  mov     rdx, rax
0x180008a60  mov     rcx, rbp
0x180008a63  call    cs:__imp_?FindString@MULTISZA@@QEAAHPEBD@Z; MULTISZA::FindString(char const *)
0x180008a69  test    eax, eax
0x180008a6b  jz      short loc_180008A7D
0x180008a6d  mov     rdx, rbx
0x180008a70  lea     rcx, [rsp+78h+var_58]
0x180008a75  call    cs:__imp_?Next@MULTISZA@@QEBAPEBDPEBD@Z; MULTISZA::Next(char const *)
0x180008a7b  jmp     short loc_180008A55
0x180008a7d  mov     esi, 1
0x180008a82  mov     rcx, rdi
0x180008a85  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180008a8b  test    esi, esi
0x180008a8d  jz      short loc_180008AE0
0x180008a8f  mov     rcx, rdi
0x180008a92  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180008a98  lea     rcx, [rsp+78h+var_58]
0x180008a9d  call    cs:__imp_?First@MULTISZA@@QEBAPEBDXZ; MULTISZA::First(void)
0x180008aa3  jmp     short loc_180008ACF
0x180008aa5  mov     rdx, rbx
0x180008aa8  mov     rcx, rbp
0x180008aab  call    cs:__imp_?FindString@MULTISZA@@QEAAHPEBD@Z; MULTISZA::FindString(char const *)
0x180008ab1  test    eax, eax
0x180008ab3  jnz     short loc_180008AC1
0x180008ab5  mov     rdx, rbx
0x180008ab8  mov     rcx, rbp
0x180008abb  call    cs:__imp_?Append@MULTISZA@@QEAAHPEBD@Z; MULTISZA::Append(char const *)
0x180008ac1  mov     rdx, rbx
0x180008ac4  lea     rcx, [rsp+78h+var_58]
0x180008ac9  call    cs:__imp_?Next@MULTISZA@@QEBAPEBDPEBD@Z; MULTISZA::Next(char const *)
0x180008acf  mov     rbx, rax
0x180008ad2  test    rax, rax
0x180008ad5  jnz     short loc_180008AA5
0x180008ad7  mov     rcx, rdi
0x180008ada  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180008ae0  lea     rcx, [rsp+78h+var_58]
0x180008ae5  call    cs:__imp_??1MULTISZA@@QEAA@XZ; MULTISZA::~MULTISZA(void)
0x180008aeb  mov     rcx, [rsp+78h+var_20]
0x180008af0  xor     rcx, rsp; StackCookie
0x180008af3  call    __security_check_cookie
0x180008af8  mov     rbx, [rsp+78h+arg_10]
0x180008b00  add     rsp, 60h
0x180008b04  pop     rdi
0x180008b05  pop     rsi
0x180008b06  pop     rbp
0x180008b07  retn
```
