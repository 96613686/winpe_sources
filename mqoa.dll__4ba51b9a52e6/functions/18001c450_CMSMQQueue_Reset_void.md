# CMSMQQueue::Reset(void)

- ea: `0x18001c450`
- end: `0x18001c4f0`
- name: `?Reset@CMSMQQueue@@UEAAJXZ`
- size: `160`
- prototype: `__int64 __fastcall(CMSMQQueue *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180005430`
- `0x18000cb34`
- `0x18001c450`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001c48b`
- `KERNEL32!LeaveCriticalSection` at `0x18001c4d7`
- `KERNEL32!LeaveCriticalSection` at `0x18001c48b`
- `KERNEL32!LeaveCriticalSection` at `0x18001c4d7`
- `mqrt!MQCreateCursor` at `0x18001c4c0`
- `mqrt!MQCreateCursor` at `0x18001c4c0`
- `mqrt!MQCloseCursor` at `0x18001c4a5`
- `mqrt!MQCloseCursor` at `0x18001c4a5`

## pseudocode

```c
__int64 __fastcall CMSMQQueue::Reset(CMSMQQueue *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  unsigned int ErrorHelper; // ebx
  HRESULT v4; // eax
  void *v5; // rcx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 72);
  CCriticalSection::Lock((CMSMQQueue *)((char *)this + 72));
  if ( *((_DWORD *)this + 44) )
  {
    v4 = 0;
    v5 = (void *)*((_QWORD *)this + 27);
    if ( v5 )
      v4 = MQCloseCursor(v5);
    *((_QWORD *)this + 27) = 0;
    if ( v4 >= 0 )
      v4 = MQCreateCursor(*((QUEUEHANDLE *)this + 21), (PHANDLE)this + 27);
    ErrorHelper = CreateErrorHelper((unsigned int)v4, 2);
    LeaveCriticalSection(v2);
  }
  else
  {
    ErrorHelper = CreateErrorHelper(2147745799LL, 2);
    LeaveCriticalSection(v2);
  }
  return ErrorHelper;
}

```

## disassembly

```asm
0x18001c450  mov     [rsp+arg_0], rbx
0x18001c455  mov     [rsp+arg_8], rsi
0x18001c45a  push    rdi
0x18001c45b  sub     rsp, 20h
0x18001c45f  mov     rbx, rcx
0x18001c462  lea     rsi, [rcx+48h]
0x18001c466  mov     rcx, rsi; this
0x18001c469  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18001c46e  cmp     dword ptr [rbx+0B0h], 0
0x18001c475  jnz     short loc_18001C494
0x18001c477  mov     edx, 2
0x18001c47c  mov     ecx, 80040007h
0x18001c481  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x18001c486  mov     ebx, eax
0x18001c488  mov     rcx, rsi; lpCriticalSection
0x18001c48b  call    cs:__imp_LeaveCriticalSection
0x18001c491  nop
0x18001c492  jmp     short loc_18001C4DE
0x18001c494  xor     eax, eax
0x18001c496  lea     rdi, [rbx+0D8h]
0x18001c49d  mov     rcx, [rdi]; hCursor
0x18001c4a0  test    rcx, rcx
0x18001c4a3  jz      short loc_18001C4AB
0x18001c4a5  call    cs:__imp_MQCloseCursor
0x18001c4ab  mov     qword ptr [rdi], 0
0x18001c4b2  test    eax, eax
0x18001c4b4  js      short loc_18001C4C6
0x18001c4b6  mov     rdx, rdi; phCursor
0x18001c4b9  mov     rcx, [rbx+0A8h]; hQueue
0x18001c4c0  call    cs:__imp_MQCreateCursor
0x18001c4c6  mov     edx, 2
0x18001c4cb  mov     ecx, eax
0x18001c4cd  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x18001c4d2  mov     ebx, eax
0x18001c4d4  mov     rcx, rsi; lpCriticalSection
0x18001c4d7  call    cs:__imp_LeaveCriticalSection
0x18001c4dd  nop
0x18001c4de  mov     eax, ebx
0x18001c4e0  mov     rbx, [rsp+28h+arg_0]
0x18001c4e5  mov     rsi, [rsp+28h+arg_8]
0x18001c4ea  add     rsp, 20h
0x18001c4ee  pop     rdi
0x18001c4ef  retn
```
