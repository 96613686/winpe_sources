# ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(ATL::CComCriticalSection &,bool)

- ea: `0x180007840`
- end: `0x18000786b`
- name: `??0?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@AEAVCComCriticalSection@1@_N@Z`
- size: `43`
- prototype: ``
- caller_count: `23`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007b44`
- `0x18001073c`
- `0x180010af0`
- `0x18001b860`
- `0x18001b9c0`
- `0x180021660`
- `0x1800222b8`
- `0x18002260c`
- `0x180022a48`
- `0x180022ba0`
- `0x180022ff8`
- `0x1800230c0`
- `0x180023250`
- `0x180023400`
- `0x1800234b0`
- `0x180023610`
- `0x1800236a0`
- `0x180023730`
- `0x180024220`
- `0x180024548`
- `0x180024784`
- `0x180024ac0`
- `0x180024ba0`

## callees

- `0x180007840`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007858`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007858`

## pseudocode

```c
__int64 __fastcall ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(
        __int64 a1,
        struct _RTL_CRITICAL_SECTION *a2,
        char a3)
{
  *(_QWORD *)a1 = a2;
  *(_BYTE *)(a1 + 8) = 0;
  if ( a3 )
  {
    EnterCriticalSection(a2);
    *(_BYTE *)(a1 + 8) = 1;
  }
  return a1;
}

```

## disassembly

```asm
0x180007840  push    rbx
0x180007842  sub     rsp, 20h
0x180007846  mov     [rcx], rdx
0x180007849  mov     rbx, rcx
0x18000784c  mov     byte ptr [rcx+8], 0
0x180007850  test    r8b, r8b
0x180007853  jz      short loc_180007862
0x180007855  mov     rcx, rdx; lpCriticalSection
0x180007858  call    cs:__imp_EnterCriticalSection
0x18000785e  mov     byte ptr [rbx+8], 1
0x180007862  mov     rax, rbx
0x180007865  add     rsp, 20h
0x180007869  pop     rbx
0x18000786a  retn
```
