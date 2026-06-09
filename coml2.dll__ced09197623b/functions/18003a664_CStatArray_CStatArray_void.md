# CStatArray::~CStatArray(void)

- ea: `0x18003a664`
- end: `0x18003a6a8`
- name: `??1CStatArray@@AEAA@XZ`
- size: `68`
- prototype: `void __fastcall(CStatArray *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024b50`

## callees

- `0x18003a664`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a683`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a697`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a683`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a697`

## pseudocode

```c
void __fastcall CStatArray::~CStatArray(CStatArray *this)
{
  LPVOID *v1; // rdi
  bool v3; // zf

  v1 = (LPVOID *)*((_QWORD *)this + 1);
  if ( v1 )
  {
    if ( *((_DWORD *)this + 4) )
    {
      do
      {
        CoTaskMemFree(*v1);
        v3 = (*((_DWORD *)this + 4))-- == 1;
        v1 += 2;
      }
      while ( !v3 );
    }
    CoTaskMemFree(*((LPVOID *)this + 1));
  }
}

```

## disassembly

```asm
0x18003a664  mov     [rsp+arg_0], rbx
0x18003a669  push    rdi
0x18003a66a  sub     rsp, 20h
0x18003a66e  mov     rdi, [rcx+8]
0x18003a672  mov     rbx, rcx
0x18003a675  test    rdi, rdi
0x18003a678  jz      short loc_18003A69D
0x18003a67a  cmp     dword ptr [rcx+10h], 0
0x18003a67e  jz      short loc_18003A693
0x18003a680  mov     rcx, [rdi]; pv
0x18003a683  call    cs:__imp_CoTaskMemFree
0x18003a689  sub     dword ptr [rbx+10h], 1
0x18003a68d  lea     rdi, [rdi+10h]
0x18003a691  jnz     short loc_18003A680
0x18003a693  mov     rcx, [rbx+8]; pv
0x18003a697  call    cs:__imp_CoTaskMemFree
0x18003a69d  mov     rbx, [rsp+28h+arg_0]
0x18003a6a2  add     rsp, 20h
0x18003a6a6  pop     rdi
0x18003a6a7  retn
```
