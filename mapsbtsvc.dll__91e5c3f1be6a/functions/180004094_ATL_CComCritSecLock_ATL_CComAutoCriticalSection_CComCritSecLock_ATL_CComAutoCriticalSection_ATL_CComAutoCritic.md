# ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)

- ea: `0x180004094`
- end: `0x1800040ba`
- name: `??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z`
- size: `38`
- prototype: `__int64 __fastcall(__int64, struct _RTL_CRITICAL_SECTION *)`
- caller_count: `13`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180004940`
- `0x180005000`
- `0x180005070`
- `0x1800051b0`
- `0x180005354`
- `0x1800056d0`
- `0x180005820`
- `0x18000bb70`
- `0x18000c348`
- `0x18000c4dc`
- `0x18000d77c`
- `0x18000f308`
- `0x18000f49c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800040a7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800040a7`

## pseudocode

```c
__int64 __fastcall ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
        __int64 a1,
        struct _RTL_CRITICAL_SECTION *a2)
{
  __int64 result; // rax

  *(_QWORD *)a1 = a2;
  *(_BYTE *)(a1 + 8) = 0;
  EnterCriticalSection(a2);
  result = a1;
  *(_BYTE *)(a1 + 8) = 1;
  return result;
}

```

## disassembly

```asm
0x180004094  push    rbx
0x180004096  sub     rsp, 20h
0x18000409a  mov     rbx, rcx
0x18000409d  mov     [rcx], rdx
0x1800040a0  mov     byte ptr [rcx+8], 0
0x1800040a4  mov     rcx, rdx; lpCriticalSection
0x1800040a7  call    cs:__imp_EnterCriticalSection
0x1800040ad  mov     rax, rbx
0x1800040b0  mov     byte ptr [rbx+8], 1
0x1800040b4  add     rsp, 20h
0x1800040b8  pop     rbx
0x1800040b9  retn
```
