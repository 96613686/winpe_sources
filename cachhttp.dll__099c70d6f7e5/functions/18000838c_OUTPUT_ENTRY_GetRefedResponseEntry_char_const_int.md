# OUTPUT_ENTRY::GetRefedResponseEntry(char const *,int *)

- ea: `0x18000838c`
- end: `0x1800084b4`
- name: `?GetRefedResponseEntry@OUTPUT_ENTRY@@QEAAPEAVRESPONSE_ENTRY@@PEBDPEAH@Z`
- size: `296`
- prototype: `struct RESPONSE_ENTRY *__fastcall(OUTPUT_ENTRY *this, const char *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002f20`

## callees

- `0x18000838c`
- `0x1800088d8`
- `0x180008bf0`

## import_xrefs

- `iisutil!?FindString@MULTISZA@@QEAAHAEAVSTRA@@@Z` at `0x1800083f6`
- `iisutil!?FindString@MULTISZA@@QEAAHAEAVSTRA@@@Z` at `0x1800083f6`
- `iisutil!?FindString@MULTISZA@@QEAAHPEBD@Z` at `0x180008454`
- `iisutil!?FindString@MULTISZA@@QEAAHPEBD@Z` at `0x180008454`
- `iisutil!?IsEmpty@MULTISZA@@QEBAHXZ` at `0x18000842d`
- `iisutil!?IsEmpty@MULTISZA@@QEBAHXZ` at `0x18000842d`
- `iisutil!?First@MULTISZA@@QEBAPEBDXZ` at `0x18000843c`
- `iisutil!?First@MULTISZA@@QEBAPEBDXZ` at `0x18000843c`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800083da`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800083da`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180008483`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180008483`
- `iisutil!??1MULTISZA@@QEAA@XZ` at `0x18000848e`
- `iisutil!??1MULTISZA@@QEAA@XZ` at `0x18000848e`
- `iisutil!??0MULTISZA@@QEAA@XZ` at `0x1800083b2`
- `iisutil!??0MULTISZA@@QEAA@XZ` at `0x1800083b2`
- `iisutil!?Next@MULTISZA@@QEBAPEBDPEBD@Z` at `0x180008466`
- `iisutil!?Next@MULTISZA@@QEBAPEBDPEBD@Z` at `0x180008466`

## pseudocode

```c
struct RESPONSE_ENTRY *__fastcall OUTPUT_ENTRY::GetRefedResponseEntry(OUTPUT_ENTRY *this, const char *a2, int *a3)
{
  __int64 v5; // rbx
  const char *i; // rax
  const char *v7; // rsi
  _BYTE v9[56]; // [rsp+20h] [rbp-58h] BYREF

  MULTISZA::MULTISZA((MULTISZA *)v9);
  if ( (int)ParseAcceptEncoding(a2, (struct MULTISZA *)v9) >= 0 )
  {
    CReaderWriterLock3::ReadLock((OUTPUT_ENTRY *)((char *)this + 816));
    if ( *((_QWORD *)this + 104) && MULTISZA::FindString((MULTISZA *)v9, (OUTPUT_ENTRY *)((char *)this + 840)) )
    {
      _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 104) + 8LL));
      v5 = *((_QWORD *)this + 104);
    }
    else
    {
      v5 = 0;
      if ( *((_QWORD *)this + 103) )
      {
        if ( *((_QWORD *)this + 104) || MULTISZA::IsEmpty((MULTISZA *)v9) )
        {
LABEL_13:
          _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 103) + 8LL));
          v5 = *((_QWORD *)this + 103);
        }
        else
        {
          for ( i = MULTISZA::First((MULTISZA *)v9); ; i = MULTISZA::Next((MULTISZA *)v9, v7) )
          {
            v7 = i;
            if ( !i )
              break;
            if ( MULTISZA::FindString((OUTPUT_ENTRY *)((char *)this + 896), i) )
              goto LABEL_13;
          }
        }
      }
    }
    CReaderWriterLock3::ReadUnlock((OUTPUT_ENTRY *)((char *)this + 816));
  }
  else
  {
    v5 = 0;
  }
  MULTISZA::~MULTISZA((MULTISZA *)v9);
  return (struct RESPONSE_ENTRY *)v5;
}

```

## disassembly

```asm
0x18000838c  mov     [rsp+arg_10], rbx
0x180008391  push    rbp
0x180008392  push    rsi
0x180008393  push    rdi
0x180008394  sub     rsp, 60h
0x180008398  mov     rax, cs:__security_cookie
0x18000839f  xor     rax, rsp
0x1800083a2  mov     [rsp+78h+var_20], rax
0x1800083a7  mov     rdi, rcx
0x1800083aa  mov     rbx, rdx
0x1800083ad  lea     rcx, [rsp+78h+var_58]
0x1800083b2  call    cs:__imp_??0MULTISZA@@QEAA@XZ; MULTISZA::MULTISZA(void)
0x1800083b8  lea     rdx, [rsp+78h+var_58]; struct MULTISZA *
0x1800083bd  mov     rcx, rbx; char *
0x1800083c0  call    ?ParseAcceptEncoding@@YAJPEBDPEAVMULTISZA@@@Z; ParseAcceptEncoding(char const *,MULTISZA *)
0x1800083c5  test    eax, eax
0x1800083c7  jns     short loc_1800083D0
0x1800083c9  xor     ebx, ebx
0x1800083cb  jmp     loc_180008489
0x1800083d0  lea     rbp, [rdi+330h]
0x1800083d7  mov     rcx, rbp
0x1800083da  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x1800083e0  cmp     qword ptr [rdi+340h], 0
0x1800083e8  jz      short loc_180008414
0x1800083ea  lea     rdx, [rdi+348h]
0x1800083f1  lea     rcx, [rsp+78h+var_58]
0x1800083f6  call    cs:__imp_?FindString@MULTISZA@@QEAAHAEAVSTRA@@@Z; MULTISZA::FindString(STRA &)
0x1800083fc  test    eax, eax
0x1800083fe  jz      short loc_180008414
0x180008400  mov     rax, [rdi+340h]
0x180008407  lock inc dword ptr [rax+8]
0x18000840b  mov     rbx, [rdi+340h]
0x180008412  jmp     short loc_180008480
0x180008414  xor     ebx, ebx
0x180008416  cmp     [rdi+338h], rbx
0x18000841d  jz      short loc_180008480
0x18000841f  cmp     [rdi+340h], rbx
0x180008426  jnz     short loc_18000846E
0x180008428  lea     rcx, [rsp+78h+var_58]
0x18000842d  call    cs:__imp_?IsEmpty@MULTISZA@@QEBAHXZ; MULTISZA::IsEmpty(void)
0x180008433  test    eax, eax
0x180008435  jnz     short loc_18000846E
0x180008437  lea     rcx, [rsp+78h+var_58]
0x18000843c  call    cs:__imp_?First@MULTISZA@@QEBAPEBDXZ; MULTISZA::First(void)
0x180008442  mov     rsi, rax
0x180008445  test    rax, rax
0x180008448  jz      short loc_180008480
0x18000844a  lea     rcx, [rdi+380h]
0x180008451  mov     rdx, rax
0x180008454  call    cs:__imp_?FindString@MULTISZA@@QEAAHPEBD@Z; MULTISZA::FindString(char const *)
0x18000845a  test    eax, eax
0x18000845c  jnz     short loc_18000846E
0x18000845e  mov     rdx, rsi
0x180008461  lea     rcx, [rsp+78h+var_58]
0x180008466  call    cs:__imp_?Next@MULTISZA@@QEBAPEBDPEBD@Z; MULTISZA::Next(char const *)
0x18000846c  jmp     short loc_180008442
0x18000846e  mov     rax, [rdi+338h]
0x180008475  lock inc dword ptr [rax+8]
0x180008479  mov     rbx, [rdi+338h]
0x180008480  mov     rcx, rbp
0x180008483  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180008489  lea     rcx, [rsp+78h+var_58]
0x18000848e  call    cs:__imp_??1MULTISZA@@QEAA@XZ; MULTISZA::~MULTISZA(void)
0x180008494  mov     rax, rbx
0x180008497  mov     rcx, [rsp+78h+var_20]
0x18000849c  xor     rcx, rsp; StackCookie
0x18000849f  call    __security_check_cookie
0x1800084a4  mov     rbx, [rsp+78h+arg_10]
0x1800084ac  add     rsp, 60h
0x1800084b0  pop     rdi
0x1800084b1  pop     rsi
0x1800084b2  pop     rbp
0x1800084b3  retn
```
