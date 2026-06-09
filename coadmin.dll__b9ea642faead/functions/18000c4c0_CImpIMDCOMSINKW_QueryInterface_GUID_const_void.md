# CImpIMDCOMSINKW::QueryInterface(_GUID const &,void * *)

- ea: `0x18000c4c0`
- end: `0x18000c527`
- name: `?QueryInterface@CImpIMDCOMSINKW@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `103`
- prototype: `__int64 __fastcall(CImpIMDCOMSINKW *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000c4c0`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CImpIMDCOMSINKW::QueryInterface(CImpIMDCOMSINKW *this, const struct _GUID *a2, void **a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( a3 )
  {
    *a3 = 0;
    if ( *(_OWORD *)a2 == *(_OWORD *)&IID_IUnknown
      || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IMDCOMSINK_W.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IMDCOMSINK_W.Data4 )
    {
      *a3 = this;
      (*(void (__fastcall **)(CImpIMDCOMSINKW *))(*(_QWORD *)this + 8LL))(this);
    }
    else
    {
      return (unsigned int)-2147467262;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x18000c4c0  push    rbx
0x18000c4c2  sub     rsp, 20h
0x18000c4c6  xor     ebx, ebx
0x18000c4c8  test    r8, r8
0x18000c4cb  jnz     short loc_18000C4D4
0x18000c4cd  mov     ebx, 80070057h
0x18000c4d2  jmp     short loc_18000C51F
0x18000c4d4  mov     [r8], rbx
0x18000c4d7  mov     rax, [rdx]
0x18000c4da  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x18000c4e1  jnz     short loc_18000C4F0
0x18000c4e3  mov     rax, [rdx+8]
0x18000c4e7  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x18000c4ee  jz      short loc_18000C509
0x18000c4f0  mov     rax, [rdx]
0x18000c4f3  cmp     rax, qword ptr cs:IID_IMDCOMSINK_W.Data1
0x18000c4fa  jnz     short loc_18000C51A
0x18000c4fc  mov     rax, [rdx+8]
0x18000c500  cmp     rax, qword ptr cs:IID_IMDCOMSINK_W.Data4
0x18000c507  jnz     short loc_18000C51A
0x18000c509  mov     [r8], rcx
0x18000c50c  mov     rax, [rcx]
0x18000c50f  mov     rax, [rax+8]
0x18000c513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c518  jmp     short loc_18000C51F
0x18000c51a  mov     ebx, 80004002h
0x18000c51f  mov     eax, ebx
0x18000c521  add     rsp, 20h
0x18000c525  pop     rbx
0x18000c526  retn
```
