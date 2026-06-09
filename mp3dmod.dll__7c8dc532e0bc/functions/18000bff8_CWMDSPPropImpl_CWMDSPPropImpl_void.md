# CWMDSPPropImpl::~CWMDSPPropImpl(void)

- ea: `0x18000bff8`
- end: `0x18000c072`
- name: `??1CWMDSPPropImpl@@QEAA@XZ`
- size: `122`
- prototype: `void __fastcall(CWMDSPPropImpl *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000be78`

## callees

- `0x18000bff8`
- `0x18000e308`
- `0x180010b30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c021`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c021`

## pseudocode

```c
void __fastcall CWMDSPPropImpl::~CWMDSPPropImpl(CWMDSPPropImpl *this)
{
  bool v1; // zf
  __int64 i; // rdi
  void *v4; // rcx

  v1 = *((_QWORD *)this + 3) == 0;
  *(_QWORD *)this = &CWMDSPPropImpl::`vftable';
  if ( !v1 )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 2); i = (unsigned int)(i + 1) )
      WMDSPPropClear(
        *(unsigned __int16 *)(96 * i + *((_QWORD *)this + 2) + 20),
        *((_QWORD *)this + 3) + 8 * ((unsigned int)i + 1LL + 8 * i));
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v4 = (void *)*((_QWORD *)this + 3);
  if ( v4 )
    operator delete(v4);
}

```

## disassembly

```asm
0x18000bff8  mov     [rsp+arg_0], rbx
0x18000bffd  push    rdi
0x18000bffe  sub     rsp, 20h
0x18000c002  cmp     qword ptr [rcx+18h], 0
0x18000c007  lea     rax, ??_7CWMDSPPropImpl@@6B@; const CWMDSPPropImpl::`vftable'
0x18000c00e  mov     [rcx], rax
0x18000c011  mov     rbx, rcx
0x18000c014  jz      short loc_18000C01D
0x18000c016  xor     edi, edi
0x18000c018  cmp     [rcx+8], edi
0x18000c01b  ja      short loc_18000C042
0x18000c01d  lea     rcx, [rbx+30h]; lpCriticalSection
0x18000c021  call    cs:__imp_DeleteCriticalSection
0x18000c027  mov     rcx, [rbx+18h]; Block
0x18000c02b  test    rcx, rcx
0x18000c02e  jnz     short loc_18000C03B
0x18000c030  mov     rbx, [rsp+28h+arg_0]
0x18000c035  add     rsp, 20h
0x18000c039  pop     rdi
0x18000c03a  retn
0x18000c03b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c040  jmp     short loc_18000C030
0x18000c042  mov     rax, [rbx+18h]
0x18000c046  mov     ecx, edi
0x18000c048  inc     rcx
0x18000c04b  lea     rcx, [rcx+rdi*8]
0x18000c04f  lea     rdx, [rax+rcx*8]
0x18000c053  mov     rcx, [rbx+10h]
0x18000c057  lea     rax, [rdi+rdi*2]
0x18000c05b  shl     rax, 5
0x18000c05f  movzx   ecx, word ptr [rax+rcx+14h]
0x18000c064  call    WMDSPPropClear
0x18000c069  inc     edi
0x18000c06b  cmp     edi, [rbx+8]
0x18000c06e  jb      short loc_18000C042
0x18000c070  jmp     short loc_18000C01D
```
