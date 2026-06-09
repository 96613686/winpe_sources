# ESIMPM::Log::Error(char const *,_GUID const *,ushort const *,...)

- ea: `0x140014f64`
- end: `0x140015081`
- name: `?Error@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ`
- size: `285`
- prototype: `void(char *, wchar_t *, const unsigned __int16 *, ...)`
- caller_count: `52`
- callee_count: `6`
- tags: ``

## callers

- `0x140015218`
- `0x14001539c`
- `0x140015520`
- `0x14001563c`
- `0x140015824`
- `0x1400159a8`
- `0x140015ad8`
- `0x140015d04`
- `0x140016094`
- `0x1400203ec`
- `0x140023034`
- `0x140023404`
- `0x140023530`
- `0x140023ba0`
- `0x140024220`
- `0x140024454`
- `0x140028160`
- `0x140029040`
- `0x140029bb0`
- `0x140029f20`
- `0x14002a854`
- `0x14002b32c`
- `0x14002b8c0`
- `0x14002bf60`
- `0x14002c0a0`
- `0x14002cb80`
- `0x14002cfb4`
- `0x14002d630`
- `0x14002d7c8`
- `0x14002d850`
- `0x14002d9a8`
- `0x14002db14`
- `0x14002dd08`
- `0x14002dfac`
- `0x14002e5b4`
- `0x14002e734`
- `0x14002eaf8`
- `0x14002eb9c`
- `0x14002fda4`
- `0x14003002c`
- `0x14003211c`
- `0x140032218`
- `0x140032434`
- `0x14003c5dd`
- `0x14003c622`
- `0x14003c667`
- `0x14003c6ac`
- `0x14003c6f1`
- `0x14003c736`
- `0x14003c77b`

## callees

- `0x140001008`
- `0x1400010e0`
- `0x140002f60`
- `0x140003b28`
- `0x140003b70`
- `0x140014f64`

## pseudocode

```c
void ESIMPM::Log::Error(char *a1, wchar_t *a2, const unsigned __int16 *a3, ...)
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
    if ( (unsigned int)dword_140075078 > 2 )
    {
      v11 = (const unsigned __int16 *)a1;
      v9 = Buffer;
      v10 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
        v6,
        (__int64)byte_140069F29,
        v7,
        v8,
        (__int64 **)&v9,
        (__int64 *)&v10,
        &v11);
    }
  }
  else if ( (unsigned int)dword_140075078 > 2 )
  {
    v9 = (wchar_t *)a1;
    v10 = Buffer;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<char>>(
      v6,
      (__int64)byte_140069F53,
      v7,
      v8,
      (__int64 **)&v10,
      (const unsigned __int16 **)&v9);
  }
}

```

## disassembly

```asm
0x140014f64  mov     [rsp-8+arg_10], r8
0x140014f69  mov     [rsp-8+Args], r9
0x140014f6e  push    rbp
0x140014f6f  push    rbx
0x140014f70  push    rsi
0x140014f71  push    rdi
0x140014f72  lea     rbp, [rsp-778h]
0x140014f7a  sub     rsp, 878h
0x140014f81  mov     rax, cs:__security_cookie
0x140014f88  xor     rax, rsp
0x140014f8b  mov     [rbp+790h+var_30], rax
0x140014f92  mov     rbx, r8
0x140014f95  mov     rdi, rdx
0x140014f98  mov     rsi, rcx
0x140014f9b  xor     edx, edx; Val
0x140014f9d  mov     r8d, 800h; Size
0x140014fa3  lea     rcx, [rsp+890h+Buffer]; void *
0x140014fa8  call    memset_0
0x140014fad  mov     r8, rbx; Format
0x140014fb0  mov     [rsp+890h+var_850], 0
0x140014fb9  mov     ebx, 3FFh
0x140014fbe  lea     r9, [rbp+790h+Args]; Args
0x140014fc5  mov     edx, ebx; BufferCount
0x140014fc7  lea     rcx, [rsp+890h+Buffer]; Buffer
0x140014fcc  call    _vsnwprintf
0x140014fd1  test    eax, eax
0x140014fd3  js      short loc_140014FD9
0x140014fd5  cmp     eax, ebx
0x140014fd7  jb      short loc_140014FE2
0x140014fd9  xor     eax, eax
0x140014fdb  mov     [rbp+790h+var_32], ax
0x140014fe2  mov     eax, cs:dword_140075078
0x140014fe8  test    rdi, rdi
0x140014feb  jz      short loc_140015032
0x140014fed  cmp     eax, 2
0x140014ff0  jbe     short loc_140015066
0x140014ff2  lea     rax, [rsp+890h+Buffer]
0x140014ff7  mov     [rsp+890h+var_840], rsi
0x140014ffc  mov     [rsp+890h+var_850], rax
0x140015001  lea     rdx, byte_140069F29
0x140015008  lea     rax, [rsp+890h+var_840]
0x14001500d  mov     [rsp+890h+var_848], rdi
0x140015012  mov     [rsp+890h+var_860], rax
0x140015017  lea     rax, [rsp+890h+var_848]
0x14001501c  mov     [rsp+890h+var_868], rax
0x140015021  lea     rax, [rsp+890h+var_850]
0x140015026  mov     [rsp+890h+var_870], rax
0x14001502b  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x140015030  jmp     short loc_140015066
0x140015032  cmp     eax, 2
0x140015035  jbe     short loc_140015066
0x140015037  lea     rax, [rsp+890h+Buffer]
0x14001503c  mov     [rsp+890h+var_850], rsi
0x140015041  mov     [rsp+890h+var_848], rax
0x140015046  lea     rdx, byte_140069F53
0x14001504d  lea     rax, [rsp+890h+var_850]
0x140015052  mov     [rsp+890h+var_868], rax
0x140015057  lea     rax, [rsp+890h+var_848]
0x14001505c  mov     [rsp+890h+var_870], rax
0x140015061  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &)
0x140015066  mov     rcx, [rbp+790h+var_30]
0x14001506d  xor     rcx, rsp; StackCookie
0x140015070  call    __security_check_cookie
0x140015075  add     rsp, 878h
0x14001507c  pop     rdi
0x14001507d  pop     rsi
0x14001507e  pop     rbx
0x14001507f  pop     rbp
0x140015080  retn
```
