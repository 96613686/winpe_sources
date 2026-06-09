# CMSMQQueueInfo::get_PathNameDNS(wchar_t * *)

- ea: `0x18001e870`
- end: `0x18001e8f9`
- name: `?get_PathNameDNS@CMSMQQueueInfo@@UEAAJPEAPEA_W@Z`
- size: `137`
- prototype: `__int64 __fastcall(CMSMQQueueInfo *__hidden this, wchar_t **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180005430`
- `0x18000cb34`
- `0x18001d8d0`
- `0x18001e870`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001e8d2`
- `KERNEL32!LeaveCriticalSection` at `0x18001e8e0`
- `KERNEL32!LeaveCriticalSection` at `0x18001e8d2`
- `KERNEL32!LeaveCriticalSection` at `0x18001e8e0`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e8b2`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e8b2`

## pseudocode

```c
__int64 __fastcall CMSMQQueueInfo::get_PathNameDNS(CMSMQQueueInfo *this, wchar_t **a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  const OLECHAR *v5; // rcx
  wchar_t *v6; // rax
  unsigned int ErrorHelper; // ebx

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 72);
  CCriticalSection::Lock((CMSMQQueueInfo *)((char *)this + 72));
  CMSMQQueueInfo::InitProps((char *)this - 8, 1);
  v5 = (const OLECHAR *)*((_QWORD *)this + 17);
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
0x18001e870  mov     [rsp+arg_0], rbx
0x18001e875  mov     [rsp+arg_8], rsi
0x18001e87a  push    rdi
0x18001e87b  sub     rsp, 20h
0x18001e87f  mov     rsi, rdx
0x18001e882  mov     rbx, rcx
0x18001e885  lea     rdi, [rcx+48h]
0x18001e889  mov     rcx, rdi; this
0x18001e88c  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18001e891  lea     rcx, [rbx-8]
0x18001e895  mov     edx, 1
0x18001e89a  call    ?InitProps@CMSMQQueueInfo@@IEAAJW4enumPropVersion@@@Z; CMSMQQueueInfo::InitProps(enumPropVersion)
0x18001e89f  mov     rcx, [rbx+88h]
0x18001e8a6  test    rcx, rcx
0x18001e8a9  jnz     short loc_18001E8B2
0x18001e8ab  lea     rcx, psz; psz
0x18001e8b2  call    cs:__imp_SysAllocString
0x18001e8b8  mov     [rsi], rax
0x18001e8bb  test    rax, rax
0x18001e8be  jnz     short loc_18001E8DD
0x18001e8c0  lea     edx, [rax+4]
0x18001e8c3  mov     ecx, 8007000Eh
0x18001e8c8  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x18001e8cd  mov     ebx, eax
0x18001e8cf  mov     rcx, rdi; lpCriticalSection
0x18001e8d2  call    cs:__imp_LeaveCriticalSection
0x18001e8d8  nop
0x18001e8d9  mov     eax, ebx
0x18001e8db  jmp     short loc_18001E8E9
0x18001e8dd  mov     rcx, rdi; lpCriticalSection
0x18001e8e0  call    cs:__imp_LeaveCriticalSection
0x18001e8e6  nop
0x18001e8e7  xor     eax, eax
0x18001e8e9  mov     rbx, [rsp+28h+arg_0]
0x18001e8ee  mov     rsi, [rsp+28h+arg_8]
0x18001e8f3  add     rsp, 20h
0x18001e8f7  pop     rdi
0x18001e8f8  retn
```
