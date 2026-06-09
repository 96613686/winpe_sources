# CMSMQQueueInfo::get_ADsPath(wchar_t * *)

- ea: `0x18001e1a0`
- end: `0x18001e229`
- name: `?get_ADsPath@CMSMQQueueInfo@@UEAAJPEAPEA_W@Z`
- size: `137`
- prototype: `__int64 __fastcall(CMSMQQueueInfo *__hidden this, wchar_t **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180005430`
- `0x18000cb34`
- `0x18001d8d0`
- `0x18001e1a0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001e202`
- `KERNEL32!LeaveCriticalSection` at `0x18001e210`
- `KERNEL32!LeaveCriticalSection` at `0x18001e202`
- `KERNEL32!LeaveCriticalSection` at `0x18001e210`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e1e2`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e1e2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMSMQQueueInfo::get_ADsPath(CMSMQQueueInfo *this, wchar_t **a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  const OLECHAR *v5; // rcx
  wchar_t *v6; // rax
  unsigned int ErrorHelper; // ebx

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 72);
  CCriticalSection::Lock((CMSMQQueueInfo *)((char *)this + 72));
  CMSMQQueueInfo::InitProps((char *)this - 8, 1);
  v5 = (const OLECHAR *)*((_QWORD *)this + 18);
  if ( !v5 )
    v5 = &psz;
  v6 = SysAllocString(v5);
  *a2 = v6;
  if ( v6 )
  {
    LeaveCriticalSection(v4);
    return 0;
  }
  else
  {
    ErrorHelper = CreateErrorHelper(-2147024882, 4);
    LeaveCriticalSection(v4);
    return ErrorHelper;
  }
}

```

## disassembly

```asm
0x18001e1a0  mov     [rsp+arg_0], rbx
0x18001e1a5  mov     [rsp+arg_8], rsi
0x18001e1aa  push    rdi
0x18001e1ab  sub     rsp, 20h
0x18001e1af  mov     rsi, rdx
0x18001e1b2  mov     rbx, rcx
0x18001e1b5  lea     rdi, [rcx+48h]
0x18001e1b9  mov     rcx, rdi; this
0x18001e1bc  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18001e1c1  lea     rcx, [rbx-8]
0x18001e1c5  mov     edx, 1
0x18001e1ca  call    ?InitProps@CMSMQQueueInfo@@IEAAJW4enumPropVersion@@@Z; CMSMQQueueInfo::InitProps(enumPropVersion)
0x18001e1cf  mov     rcx, [rbx+90h]
0x18001e1d6  test    rcx, rcx
0x18001e1d9  jnz     short loc_18001E1E2
0x18001e1db  lea     rcx, psz; psz
0x18001e1e2  call    cs:__imp_SysAllocString
0x18001e1e8  mov     [rsi], rax
0x18001e1eb  test    rax, rax
0x18001e1ee  jnz     short loc_18001E20D
0x18001e1f0  lea     edx, [rax+4]
0x18001e1f3  mov     ecx, 8007000Eh
0x18001e1f8  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x18001e1fd  mov     ebx, eax
0x18001e1ff  mov     rcx, rdi; lpCriticalSection
0x18001e202  call    cs:__imp_LeaveCriticalSection
0x18001e208  nop
0x18001e209  mov     eax, ebx
0x18001e20b  jmp     short loc_18001E219
0x18001e20d  mov     rcx, rdi; lpCriticalSection
0x18001e210  call    cs:__imp_LeaveCriticalSection
0x18001e216  nop
0x18001e217  xor     eax, eax
0x18001e219  mov     rbx, [rsp+28h+arg_0]
0x18001e21e  mov     rsi, [rsp+28h+arg_8]
0x18001e223  add     rsp, 20h
0x18001e227  pop     rdi
0x18001e228  retn
```
