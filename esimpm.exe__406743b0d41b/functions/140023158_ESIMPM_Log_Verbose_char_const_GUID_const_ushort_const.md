# ESIMPM::Log::Verbose(char const *,_GUID const *,ushort const *,...)

- ea: `0x140023158`
- end: `0x140023275`
- name: `?Verbose@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ`
- size: `285`
- prototype: `static void(const char *, const struct _GUID *, const unsigned __int16 *, ...)`
- caller_count: `26`
- callee_count: `6`
- tags: ``

## callers

- `0x140023034`
- `0x1400230dc`
- `0x140024900`
- `0x140025830`
- `0x140028774`
- `0x140029040`
- `0x14002a188`
- `0x14002aa1c`
- `0x14002acf8`
- `0x14002b090`
- `0x14002b32c`
- `0x14002b46c`
- `0x14002b8c0`
- `0x14002b9f8`
- `0x14002bae4`
- `0x14002bbd0`
- `0x14002bc98`
- `0x14002be60`
- `0x14002bf60`
- `0x14002c0a0`
- `0x14002c528`
- `0x14002ca30`
- `0x14002cb80`
- `0x14002f654`
- `0x14003377c`
- `0x140033a3c`

## callees

- `0x140001008`
- `0x1400010e0`
- `0x140002f60`
- `0x140003b28`
- `0x140003b70`
- `0x140023158`

## pseudocode

```c
void ESIMPM::Log::Verbose(char *a1, wchar_t *a2, const unsigned __int16 *a3, ...)
{
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  wchar_t *v9; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *v10; // [rsp+48h] [rbp-B8h] BYREF
  const unsigned __int16 *v11; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Buffer[1024]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 Args; // [rsp+8B8h] [rbp+7B8h] BYREF
  va_list Argsa; // [rsp+8B8h] [rbp+7B8h]
  va_list va1; // [rsp+8C0h] [rbp+7C0h] BYREF

  va_start(va1, a3);
  va_start(Argsa, a3);
  Args = va_arg(va1, _QWORD);
  memset_0(Buffer, 0, sizeof(Buffer));
  v9 = 0;
  if ( (unsigned int)vsnwprintf(Buffer, 0x3FFu, a3, Argsa) > 0x3FE )
    Buffer[1023] = 0;
  if ( a2 )
  {
    if ( (unsigned int)dword_140075078 > 5 )
    {
      v11 = (const unsigned __int16 *)a1;
      v9 = Buffer;
      v10 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
        v6,
        (__int64)word_14006A2E2,
        v7,
        v8,
        (__int64 **)&v9,
        (__int64 *)&v10,
        &v11);
    }
  }
  else if ( (unsigned int)dword_140075078 > 5 )
  {
    v9 = (wchar_t *)a1;
    v10 = Buffer;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<char>>(
      v6,
      (__int64)&dword_14006A30C,
      v7,
      v8,
      (__int64 **)&v10,
      (const unsigned __int16 **)&v9);
  }
}

```

## disassembly

```asm
0x140023158  mov     [rsp-8+arg_10], r8
0x14002315d  mov     [rsp-8+Args], r9
0x140023162  push    rbp
0x140023163  push    rbx
0x140023164  push    rsi
0x140023165  push    rdi
0x140023166  lea     rbp, [rsp-778h]
0x14002316e  sub     rsp, 878h
0x140023175  mov     rax, cs:__security_cookie
0x14002317c  xor     rax, rsp
0x14002317f  mov     [rbp+790h+var_30], rax
0x140023186  mov     rbx, r8
0x140023189  mov     rdi, rdx
0x14002318c  mov     rsi, rcx
0x14002318f  xor     edx, edx; Val
0x140023191  mov     r8d, 800h; Size
0x140023197  lea     rcx, [rsp+890h+Buffer]; void *
0x14002319c  call    memset_0
0x1400231a1  mov     r8, rbx; Format
0x1400231a4  mov     [rsp+890h+var_850], 0
0x1400231ad  mov     ebx, 3FFh
0x1400231b2  lea     r9, [rbp+790h+Args]; Args
0x1400231b9  mov     edx, ebx; BufferCount
0x1400231bb  lea     rcx, [rsp+890h+Buffer]; Buffer
0x1400231c0  call    _vsnwprintf
0x1400231c5  test    eax, eax
0x1400231c7  js      short loc_1400231CD
0x1400231c9  cmp     eax, ebx
0x1400231cb  jb      short loc_1400231D6
0x1400231cd  xor     eax, eax
0x1400231cf  mov     [rbp+790h+var_32], ax
0x1400231d6  mov     eax, cs:dword_140075078
0x1400231dc  test    rdi, rdi
0x1400231df  jz      short loc_140023226
0x1400231e1  cmp     eax, 5
0x1400231e4  jbe     short loc_14002325A
0x1400231e6  lea     rax, [rsp+890h+Buffer]
0x1400231eb  mov     [rsp+890h+var_840], rsi
0x1400231f0  mov     [rsp+890h+var_850], rax
0x1400231f5  lea     rdx, word_14006A2E2
0x1400231fc  lea     rax, [rsp+890h+var_840]
0x140023201  mov     [rsp+890h+var_848], rdi
0x140023206  mov     [rsp+890h+var_860], rax
0x14002320b  lea     rax, [rsp+890h+var_848]
0x140023210  mov     [rsp+890h+var_868], rax
0x140023215  lea     rax, [rsp+890h+var_850]
0x14002321a  mov     [rsp+890h+var_870], rax
0x14002321f  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x140023224  jmp     short loc_14002325A
0x140023226  cmp     eax, 5
0x140023229  jbe     short loc_14002325A
0x14002322b  lea     rax, [rsp+890h+Buffer]
0x140023230  mov     [rsp+890h+var_850], rsi
0x140023235  mov     [rsp+890h+var_848], rax
0x14002323a  lea     rdx, dword_14006A30C
0x140023241  lea     rax, [rsp+890h+var_850]
0x140023246  mov     [rsp+890h+var_868], rax
0x14002324b  lea     rax, [rsp+890h+var_848]
0x140023250  mov     [rsp+890h+var_870], rax
0x140023255  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &)
0x14002325a  mov     rcx, [rbp+790h+var_30]
0x140023261  xor     rcx, rsp; StackCookie
0x140023264  call    __security_check_cookie
0x140023269  add     rsp, 878h
0x140023270  pop     rdi
0x140023271  pop     rsi
0x140023272  pop     rbx
0x140023273  pop     rbp
0x140023274  retn
```
