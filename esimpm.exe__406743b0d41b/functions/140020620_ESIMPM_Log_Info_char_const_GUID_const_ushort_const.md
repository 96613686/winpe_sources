# ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)

- ea: `0x140020620`
- end: `0x14002073d`
- name: `?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ`
- size: `285`
- prototype: `static void(const char *, const struct _GUID *, const unsigned __int16 *, ...)`
- caller_count: `59`
- callee_count: `6`
- tags: ``

## callers

- `0x140020168`
- `0x1400203ec`
- `0x140023404`
- `0x140023ba0`
- `0x140024220`
- `0x140024454`
- `0x140024564`
- `0x140024790`
- `0x140024c20`
- `0x140025830`
- `0x1400258a0`
- `0x14002595c`
- `0x140025e00`
- `0x140027e3c`
- `0x140028160`
- `0x140028620`
- `0x140028774`
- `0x140029040`
- `0x140029aec`
- `0x140029bb0`
- `0x14002a188`
- `0x14002a4b8`
- `0x14002a854`
- `0x14002b090`
- `0x14002b46c`
- `0x14002b9f8`
- `0x14002bae4`
- `0x14002c528`
- `0x14002ca30`
- `0x14002cfb4`
- `0x14002d850`
- `0x14002d9a8`
- `0x14002db14`
- `0x14002dd08`
- `0x14002dfac`
- `0x14002e5b4`
- `0x14002e734`
- `0x14002ea68`
- `0x14002eaf8`
- `0x14002eb9c`
- `0x14002f214`
- `0x14002f654`
- `0x14002f9e0`
- `0x14002fda4`
- `0x14003002c`
- `0x140030248`
- `0x1400309bc`
- `0x140030ee0`
- `0x14003110c`
- `0x1400311ec`

## callees

- `0x140001008`
- `0x1400010e0`
- `0x140002f60`
- `0x140003b28`
- `0x140003b70`
- `0x140020620`

## pseudocode

```c
void ESIMPM::Log::Info(char *a1, wchar_t *a2, const unsigned __int16 *a3, ...)
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
    if ( (unsigned int)dword_140075078 > 4 )
    {
      v11 = (const unsigned __int16 *)a1;
      v9 = Buffer;
      v10 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
        v6,
        (__int64)&word_14006A0A6,
        v7,
        v8,
        (__int64 **)&v9,
        (__int64 *)&v10,
        &v11);
    }
  }
  else if ( (unsigned int)dword_140075078 > 4 )
  {
    v9 = (wchar_t *)a1;
    v10 = Buffer;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<char>>(
      v6,
      (__int64)qword_14006A0D0,
      v7,
      v8,
      (__int64 **)&v10,
      (const unsigned __int16 **)&v9);
  }
}

```

## disassembly

```asm
0x140020620  mov     [rsp-8+arg_10], r8
0x140020625  mov     [rsp-8+Args], r9
0x14002062a  push    rbp
0x14002062b  push    rbx
0x14002062c  push    rsi
0x14002062d  push    rdi
0x14002062e  lea     rbp, [rsp-778h]
0x140020636  sub     rsp, 878h
0x14002063d  mov     rax, cs:__security_cookie
0x140020644  xor     rax, rsp
0x140020647  mov     [rbp+790h+var_30], rax
0x14002064e  mov     rbx, r8
0x140020651  mov     rdi, rdx
0x140020654  mov     rsi, rcx
0x140020657  xor     edx, edx; Val
0x140020659  mov     r8d, 800h; Size
0x14002065f  lea     rcx, [rsp+890h+Buffer]; void *
0x140020664  call    memset_0
0x140020669  mov     r8, rbx; Format
0x14002066c  mov     [rsp+890h+var_850], 0
0x140020675  mov     ebx, 3FFh
0x14002067a  lea     r9, [rbp+790h+Args]; Args
0x140020681  mov     edx, ebx; BufferCount
0x140020683  lea     rcx, [rsp+890h+Buffer]; Buffer
0x140020688  call    _vsnwprintf
0x14002068d  test    eax, eax
0x14002068f  js      short loc_140020695
0x140020691  cmp     eax, ebx
0x140020693  jb      short loc_14002069E
0x140020695  xor     eax, eax
0x140020697  mov     [rbp+790h+var_32], ax
0x14002069e  mov     eax, cs:dword_140075078
0x1400206a4  test    rdi, rdi
0x1400206a7  jz      short loc_1400206EE
0x1400206a9  cmp     eax, 4
0x1400206ac  jbe     short loc_140020722
0x1400206ae  lea     rax, [rsp+890h+Buffer]
0x1400206b3  mov     [rsp+890h+var_840], rsi
0x1400206b8  mov     [rsp+890h+var_850], rax
0x1400206bd  lea     rdx, word_14006A0A6
0x1400206c4  lea     rax, [rsp+890h+var_840]
0x1400206c9  mov     [rsp+890h+var_848], rdi
0x1400206ce  mov     [rsp+890h+var_860], rax
0x1400206d3  lea     rax, [rsp+890h+var_848]
0x1400206d8  mov     [rsp+890h+var_868], rax
0x1400206dd  lea     rax, [rsp+890h+var_850]
0x1400206e2  mov     [rsp+890h+var_870], rax
0x1400206e7  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x1400206ec  jmp     short loc_140020722
0x1400206ee  cmp     eax, 4
0x1400206f1  jbe     short loc_140020722
0x1400206f3  lea     rax, [rsp+890h+Buffer]
0x1400206f8  mov     [rsp+890h+var_850], rsi
0x1400206fd  mov     [rsp+890h+var_848], rax
0x140020702  lea     rdx, qword_14006A0D0
0x140020709  lea     rax, [rsp+890h+var_850]
0x14002070e  mov     [rsp+890h+var_868], rax
0x140020713  lea     rax, [rsp+890h+var_848]
0x140020718  mov     [rsp+890h+var_870], rax
0x14002071d  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &)
0x140020722  mov     rcx, [rbp+790h+var_30]
0x140020729  xor     rcx, rsp; StackCookie
0x14002072c  call    __security_check_cookie
0x140020731  add     rsp, 878h
0x140020738  pop     rdi
0x140020739  pop     rsi
0x14002073a  pop     rbx
0x14002073b  pop     rbp
0x14002073c  retn
```
