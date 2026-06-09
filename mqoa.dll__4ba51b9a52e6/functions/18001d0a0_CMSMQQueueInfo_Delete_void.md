# CMSMQQueueInfo::Delete(void)

- ea: `0x18001d0a0`
- end: `0x18001d0f8`
- name: `?Delete@CMSMQQueueInfo@@UEAAJXZ`
- size: `88`
- prototype: `__int64 __fastcall(CMSMQQueueInfo *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callees

- `0x180005430`
- `0x18000cb34`
- `0x18001d0a0`
- `0x18001e10c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001d0e4`
- `KERNEL32!LeaveCriticalSection` at `0x18001d0e4`
- `mqrt!MQDeleteQueue` at `0x18001d0cd`
- `mqrt!MQDeleteQueue` at `0x18001d0cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMSMQQueueInfo::Delete(LPCWSTR *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  HRESULT updated; // eax
  unsigned int ErrorHelper; // ebx

  v2 = (struct _RTL_CRITICAL_SECTION *)(this + 9);
  CCriticalSection::Lock((CCriticalSection *)(this + 9));
  updated = CMSMQQueueInfo::UpdateFormatName((CMSMQQueueInfo *)(this - 1));
  if ( updated >= 0 )
    updated = MQDeleteQueue(this[19]);
  ErrorHelper = CreateErrorHelper((unsigned int)updated, 4);
  LeaveCriticalSection(v2);
  return ErrorHelper;
}

```

## disassembly

```asm
0x18001d0a0  mov     [rsp+arg_0], rbx
0x18001d0a5  push    rdi
0x18001d0a6  sub     rsp, 20h
0x18001d0aa  mov     rbx, rcx
0x18001d0ad  lea     rdi, [rcx+48h]
0x18001d0b1  mov     rcx, rdi; this
0x18001d0b4  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18001d0b9  lea     rcx, [rbx-8]; this
0x18001d0bd  call    ?UpdateFormatName@CMSMQQueueInfo@@IEAAJXZ; CMSMQQueueInfo::UpdateFormatName(void)
0x18001d0c2  test    eax, eax
0x18001d0c4  js      short loc_18001D0D3
0x18001d0c6  mov     rcx, [rbx+98h]; lpwcsFormatName
0x18001d0cd  call    cs:__imp_MQDeleteQueue
0x18001d0d3  mov     edx, 4
0x18001d0d8  mov     ecx, eax
0x18001d0da  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x18001d0df  mov     ebx, eax
0x18001d0e1  mov     rcx, rdi; lpCriticalSection
0x18001d0e4  call    cs:__imp_LeaveCriticalSection
0x18001d0ea  nop
0x18001d0eb  mov     eax, ebx
0x18001d0ed  mov     rbx, [rsp+28h+arg_0]
0x18001d0f2  add     rsp, 20h
0x18001d0f6  pop     rdi
0x18001d0f7  retn
```
