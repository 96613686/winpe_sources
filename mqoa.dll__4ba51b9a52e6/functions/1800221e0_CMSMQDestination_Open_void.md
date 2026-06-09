# CMSMQDestination::Open(void)

- ea: `0x1800221e0`
- end: `0x180022277`
- name: `?Open@CMSMQDestination@@UEAAJXZ`
- size: `151`
- prototype: `__int64 __fastcall(CMSMQDestination *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180005430`
- `0x18000cb34`
- `0x1800221e0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180022217`
- `KERNEL32!LeaveCriticalSection` at `0x180022263`
- `KERNEL32!LeaveCriticalSection` at `0x180022217`
- `KERNEL32!LeaveCriticalSection` at `0x180022263`
- `mqrt!MQOpenQueue` at `0x18002223a`
- `mqrt!MQOpenQueue` at `0x18002223a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMSMQDestination::Open(CMSMQDestination *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  HRESULT v3; // eax
  const WCHAR *v4; // rcx
  unsigned int ErrorHelper; // ebx
  QUEUEHANDLE phQueue; // [rsp+30h] [rbp+8h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 80);
  CCriticalSection::Lock((CMSMQDestination *)((char *)this + 80));
  v3 = -2147024809;
  v4 = (const WCHAR *)*((_QWORD *)this + 17);
  if ( v4 )
  {
    if ( *((_QWORD *)this + 18) != -1 )
    {
      LeaveCriticalSection(v2);
      return 1;
    }
    phQueue = 0;
    v3 = MQOpenQueue(v4, 2u, 0, &phQueue);
    if ( v3 >= 0 )
    {
      *((_QWORD *)this + 18) = phQueue;
      v3 = 0;
    }
  }
  ErrorHelper = CreateErrorHelper((unsigned int)v3, 10);
  LeaveCriticalSection(v2);
  return ErrorHelper;
}

```

## disassembly

```asm
0x1800221e0  mov     [rsp+arg_8], rbx
0x1800221e5  push    rdi
0x1800221e6  sub     rsp, 20h
0x1800221ea  mov     rbx, rcx
0x1800221ed  lea     rdi, [rcx+50h]
0x1800221f1  mov     rcx, rdi; this
0x1800221f4  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x1800221f9  mov     eax, 80070057h
0x1800221fe  mov     rcx, [rbx+88h]; lpwcsFormatName
0x180022205  test    rcx, rcx
0x180022208  jz      short loc_180022252
0x18002220a  cmp     qword ptr [rbx+90h], 0FFFFFFFFFFFFFFFFh
0x180022212  jz      short loc_180022225
0x180022214  mov     rcx, rdi; lpCriticalSection
0x180022217  call    cs:__imp_LeaveCriticalSection
0x18002221d  nop
0x18002221e  mov     eax, 1
0x180022223  jmp     short loc_18002226C
0x180022225  mov     [rsp+28h+phQueue], 0
0x18002222e  lea     r9, [rsp+28h+phQueue]; phQueue
0x180022233  xor     r8d, r8d; dwShareMode
0x180022236  lea     edx, [r8+2]; dwAccess
0x18002223a  call    cs:__imp_MQOpenQueue
0x180022240  test    eax, eax
0x180022242  js      short loc_180022252
0x180022244  mov     rax, [rsp+28h+phQueue]
0x180022249  mov     [rbx+90h], rax
0x180022250  xor     eax, eax
0x180022252  mov     edx, 0Ah
0x180022257  mov     ecx, eax
0x180022259  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x18002225e  mov     ebx, eax
0x180022260  mov     rcx, rdi; lpCriticalSection
0x180022263  call    cs:__imp_LeaveCriticalSection
0x180022269  nop
0x18002226a  mov     eax, ebx
0x18002226c  mov     rbx, [rsp+28h+arg_8]
0x180022271  add     rsp, 20h
0x180022275  pop     rdi
0x180022276  retn
```
