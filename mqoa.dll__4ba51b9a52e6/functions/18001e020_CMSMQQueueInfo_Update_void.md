# CMSMQQueueInfo::Update(void)

- ea: `0x18001e020`
- end: `0x18001e104`
- name: `?Update@CMSMQQueueInfo@@UEAAJXZ`
- size: `228`
- prototype: `__int64 __fastcall(CMSMQQueueInfo *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x180005430`
- `0x18000cb34`
- `0x18001cd7c`
- `0x18001d17c`
- `0x18001e020`
- `0x18001e10c`
- `0x180026990`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001e0f2`
- `KERNEL32!LeaveCriticalSection` at `0x18001e0f2`
- `mqrt!MQSetQueueProperties` at `0x18001e0ce`
- `mqrt!MQSetQueueProperties` at `0x18001e0ce`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMSMQQueueInfo::Update(CMSMQQueueInfo *this)
{
  signed int updated; // ebx
  const unsigned int *v3; // rax
  unsigned int v4; // r8d
  unsigned int ErrorHelper; // ebx
  MQQUEUEPROPS pQueueProps; // [rsp+30h] [rbp-48h] BYREF

  CCriticalSection::Lock((CMSMQQueueInfo *)((char *)this + 72));
  memset(&pQueueProps, 0, sizeof(pQueueProps));
  updated = CMSMQQueueInfo::UpdateFormatName((CMSMQQueueInfo *)((char *)this - 8));
  if ( updated >= 0 )
  {
    if ( (unsigned int)GetFormatNameType(*((_QWORD *)this + 19)) == 2 )
    {
      v3 = &qword_18002F9A0;
      v4 = 8;
    }
    else
    {
      v3 = (const unsigned int *)qword_18002F9C0;
      v4 = 9;
    }
    updated = CMSMQQueueInfo::CreateQueueProps(
                (CMSMQQueueInfo *)((char *)this - 8),
                1,
                v4,
                &pQueueProps,
                *((_DWORD *)this + 44),
                v3);
    if ( updated >= 0 )
    {
      updated = CMSMQQueueInfo::UpdateFormatName((CMSMQQueueInfo *)((char *)this - 8));
      if ( updated >= 0 )
        updated = MQSetQueueProperties(*((LPCWSTR *)this + 19), &pQueueProps);
    }
  }
  CMSMQQueueInfo::FreeQueueProps(&pQueueProps);
  ErrorHelper = CreateErrorHelper(updated, 4);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  return ErrorHelper;
}

```

## disassembly

```asm
0x18001e020  push    rbx
0x18001e022  push    rbp
0x18001e023  push    rsi
0x18001e024  push    rdi
0x18001e025  sub     rsp, 58h
0x18001e029  mov     rdi, rcx
0x18001e02c  add     rcx, 48h ; 'H'; this
0x18001e030  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18001e035  mov     qword ptr [rsp+78h+pQueueProps.cProp], 0
0x18001e03e  xorps   xmm0, xmm0
0x18001e041  movdqu  xmmword ptr [rsp+78h+pQueueProps.aPropID], xmm0
0x18001e047  mov     [rsp+78h+pQueueProps.aStatus], 0
0x18001e050  lea     rsi, [rdi-8]
0x18001e054  mov     rcx, rsi; this
0x18001e057  call    ?UpdateFormatName@CMSMQQueueInfo@@IEAAJXZ; CMSMQQueueInfo::UpdateFormatName(void)
0x18001e05c  mov     ebx, eax
0x18001e05e  test    eax, eax
0x18001e060  js      short loc_18001E0D6
0x18001e062  mov     rcx, [rdi+98h]
0x18001e069  call    ?GetFormatNameType@@YA?AW4QUEUE_FORMAT_TYPE@@PEA_W@Z; GetFormatNameType(wchar_t *)
0x18001e06e  mov     ecx, [rdi+0B0h]
0x18001e074  lea     r9, [rsp+78h+pQueueProps]; struct tagMQQUEUEPROPS *
0x18001e079  mov     edx, 1; int
0x18001e07e  cmp     eax, 2
0x18001e081  jnz     short loc_18001E090
0x18001e083  lea     rax, qword_18002F9A0
0x18001e08a  lea     r8d, [rdx+7]
0x18001e08e  jmp     short loc_18001E09D
0x18001e090  lea     rax, qword_18002F9C0
0x18001e097  mov     r8d, 9; unsigned int
0x18001e09d  mov     [rsp+78h+var_50], rax; unsigned int *
0x18001e0a2  mov     [rsp+78h+var_58], ecx; int
0x18001e0a6  mov     rcx, rsi; this
0x18001e0a9  call    ?CreateQueueProps@CMSMQQueueInfo@@IEAAJHIPEAUtagMQQUEUEPROPS@@HQEBK@Z; CMSMQQueueInfo::CreateQueueProps(int,uint,tagMQQUEUEPROPS *,int,ulong const * const)
0x18001e0ae  test    eax, eax
0x18001e0b0  mov     ebx, eax
0x18001e0b2  js      short loc_18001E0D6
0x18001e0b4  mov     rcx, rsi; this
0x18001e0b7  call    ?UpdateFormatName@CMSMQQueueInfo@@IEAAJXZ; CMSMQQueueInfo::UpdateFormatName(void)
0x18001e0bc  mov     ebx, eax
0x18001e0be  test    eax, eax
0x18001e0c0  js      short loc_18001E0D6
0x18001e0c2  lea     rdx, [rsp+78h+pQueueProps]; pQueueProps
0x18001e0c7  mov     rcx, [rdi+98h]; lpwcsFormatName
0x18001e0ce  call    cs:__imp_MQSetQueueProperties
0x18001e0d4  mov     ebx, eax
0x18001e0d6  lea     rcx, [rsp+78h+pQueueProps]; struct tagMQQUEUEPROPS *
0x18001e0db  call    ?FreeQueueProps@CMSMQQueueInfo@@KAXPEAUtagMQQUEUEPROPS@@@Z; CMSMQQueueInfo::FreeQueueProps(tagMQQUEUEPROPS *)
0x18001e0e0  mov     edx, 4
0x18001e0e5  mov     ecx, ebx
0x18001e0e7  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x18001e0ec  mov     ebx, eax
0x18001e0ee  lea     rcx, [rdi+48h]; lpCriticalSection
0x18001e0f2  call    cs:__imp_LeaveCriticalSection
0x18001e0f8  nop
0x18001e0f9  mov     eax, ebx
0x18001e0fb  add     rsp, 58h
0x18001e0ff  pop     rdi
0x18001e100  pop     rsi
0x18001e101  pop     rbp
0x18001e102  pop     rbx
0x18001e103  retn
```
