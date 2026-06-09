# CMSMQQueueInfo::get_PathName(wchar_t * *)

- ea: `0x18001e7e0`
- end: `0x18001e866`
- name: `?get_PathName@CMSMQQueueInfo@@UEAAJPEAPEA_W@Z`
- size: `134`
- prototype: `__int64 __fastcall(CMSMQQueueInfo *__hidden this, wchar_t **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180005430`
- `0x18000cb34`
- `0x18001d8d0`
- `0x18001e7e0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001e83f`
- `KERNEL32!LeaveCriticalSection` at `0x18001e84d`
- `KERNEL32!LeaveCriticalSection` at `0x18001e83f`
- `KERNEL32!LeaveCriticalSection` at `0x18001e84d`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e81f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e81f`

## pseudocode

```c
__int64 __fastcall CMSMQQueueInfo::get_PathName(CMSMQQueueInfo *this, wchar_t **a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  const OLECHAR *v5; // rcx
  wchar_t *v6; // rax
  unsigned int ErrorHelper; // ebx

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 72);
  CCriticalSection::Lock((CMSMQQueueInfo *)((char *)this + 72));
  CMSMQQueueInfo::InitProps((char *)this - 8, 0);
  v5 = (const OLECHAR *)*((_QWORD *)this + 21);
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
0x18001e7e0  mov     [rsp+arg_0], rbx
0x18001e7e5  mov     [rsp+arg_8], rsi
0x18001e7ea  push    rdi
0x18001e7eb  sub     rsp, 20h
0x18001e7ef  mov     rsi, rdx
0x18001e7f2  mov     rbx, rcx
0x18001e7f5  lea     rdi, [rcx+48h]
0x18001e7f9  mov     rcx, rdi; this
0x18001e7fc  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18001e801  lea     rcx, [rbx-8]
0x18001e805  xor     edx, edx
0x18001e807  call    ?InitProps@CMSMQQueueInfo@@IEAAJW4enumPropVersion@@@Z; CMSMQQueueInfo::InitProps(enumPropVersion)
0x18001e80c  mov     rcx, [rbx+0A8h]
0x18001e813  test    rcx, rcx
0x18001e816  jnz     short loc_18001E81F
0x18001e818  lea     rcx, psz; psz
0x18001e81f  call    cs:__imp_SysAllocString
0x18001e825  mov     [rsi], rax
0x18001e828  test    rax, rax
0x18001e82b  jnz     short loc_18001E84A
0x18001e82d  lea     edx, [rax+4]
0x18001e830  mov     ecx, 8007000Eh
0x18001e835  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x18001e83a  mov     ebx, eax
0x18001e83c  mov     rcx, rdi; lpCriticalSection
0x18001e83f  call    cs:__imp_LeaveCriticalSection
0x18001e845  nop
0x18001e846  mov     eax, ebx
0x18001e848  jmp     short loc_18001E856
0x18001e84a  mov     rcx, rdi; lpCriticalSection
0x18001e84d  call    cs:__imp_LeaveCriticalSection
0x18001e853  nop
0x18001e854  xor     eax, eax
0x18001e856  mov     rbx, [rsp+28h+arg_0]
0x18001e85b  mov     rsi, [rsp+28h+arg_8]
0x18001e860  add     rsp, 20h
0x18001e864  pop     rdi
0x18001e865  retn
```
