# CIEAdminBrokerObject::Release(void)

- ea: `0x140008230`
- end: `0x140008273`
- name: `?Release@CIEAdminBrokerObject@@UEAAKXZ`
- size: `67`
- prototype: `unsigned int __fastcall(CIEAdminBrokerObject *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140008280`
- `0x140008290`

## callees

- `0x1400039bc`
- `0x140007bcc`
- `0x140008230`

## pseudocode

```c
__int64 __fastcall CIEAdminBrokerObject::Release(CIEAdminBrokerObject *this)
{
  int v1; // edi
  unsigned int v3; // edi

  v1 = *((_DWORD *)this + 6);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 6, 0xFFFFFFFF) == 1 )
  {
    v3 = 0;
    if ( this )
    {
      CIEAdminBrokerObject::~CIEAdminBrokerObject(this);
      operator delete(this);
    }
  }
  else
  {
    return (unsigned int)(v1 - 1);
  }
  return v3;
}

```

## disassembly

```asm
0x140008230  mov     [rsp+arg_0], rbx
0x140008235  push    rdi
0x140008236  sub     rsp, 20h
0x14000823a  mov     edi, [rcx+18h]
0x14000823d  mov     rbx, rcx
0x140008240  or      eax, 0FFFFFFFFh
0x140008243  lock xadd [rcx+18h], eax
0x140008248  cmp     eax, 1
0x14000824b  jnz     short loc_140008263
0x14000824d  xor     edi, edi
0x14000824f  test    rcx, rcx
0x140008252  jz      short loc_140008265
0x140008254  call    ??1CIEAdminBrokerObject@@QEAA@XZ; CIEAdminBrokerObject::~CIEAdminBrokerObject(void)
0x140008259  mov     rcx, rbx; lpMem
0x14000825c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140008261  jmp     short loc_140008265
0x140008263  dec     edi
0x140008265  mov     rbx, [rsp+28h+arg_0]
0x14000826a  mov     eax, edi
0x14000826c  add     rsp, 20h
0x140008270  pop     rdi
0x140008271  retn
```
