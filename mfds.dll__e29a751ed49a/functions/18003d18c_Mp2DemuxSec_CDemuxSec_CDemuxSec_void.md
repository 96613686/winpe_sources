# Mp2DemuxSec::CDemuxSec::~CDemuxSec(void)

- ea: `0x18003d18c`
- end: `0x18003d224`
- name: `??1CDemuxSec@Mp2DemuxSec@@UEAA@XZ`
- size: `152`
- prototype: `void __fastcall(Mp2DemuxSec::CDemuxSec *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18003d078`
- `0x18004ec10`
- `0x180099fe0`
- `0x1800a48a0`

## callees

- `0x18003d18c`
- `0x180073d4c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d1f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d20c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d1f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003d20c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003d1ba`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003d1e2`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003d1ba`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003d1e2`

## pseudocode

```c
void __fastcall Mp2DemuxSec::CDemuxSec::~CDemuxSec(Mp2DemuxSec::CDemuxSec *this)
{
  bool v1; // zf
  __int64 i; // rdi
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx

  v1 = *((_QWORD *)this + 6) == 0;
  *(_QWORD *)this = &Mp2DemuxSec::CDemuxSec::`vftable';
  if ( !v1 )
  {
    for ( i = 0; (unsigned int)i < *((unsigned __int8 *)this + 56); i = (unsigned int)(i + 1) )
      FreeSid(*(PSID *)(*((_QWORD *)this + 6) + 8 * i));
    operator delete(*((void **)this + 6));
  }
  v4 = (void *)*((_QWORD *)this + 8);
  if ( v4 )
    FreeSid(v4);
  v5 = (void *)*((_QWORD *)this + 1);
  if ( v5 )
    LocalFree(v5);
  v6 = (void *)*((_QWORD *)this + 9);
  if ( v6 )
    LocalFree(v6);
}

```

## disassembly

```asm
0x18003d18c  mov     [rsp+arg_0], rbx
0x18003d191  push    rdi
0x18003d192  sub     rsp, 20h
0x18003d196  cmp     qword ptr [rcx+30h], 0
0x18003d19b  lea     rax, ??_7CDemuxSec@Mp2DemuxSec@@6B@; const Mp2DemuxSec::CDemuxSec::`vftable'
0x18003d1a2  mov     [rcx], rax
0x18003d1a5  mov     rbx, rcx
0x18003d1a8  jz      short loc_18003D1D9
0x18003d1aa  xor     edi, edi
0x18003d1ac  cmp     [rcx+38h], dil
0x18003d1b0  jbe     short loc_18003D1D0
0x18003d1b2  mov     rcx, [rbx+30h]
0x18003d1b6  mov     rcx, [rcx+rdi*8]; pSid
0x18003d1ba  call    cs:__imp_FreeSid
0x18003d1c1  nop     dword ptr [rax+rax+00h]
0x18003d1c6  movzx   eax, byte ptr [rbx+38h]
0x18003d1ca  inc     edi
0x18003d1cc  cmp     edi, eax
0x18003d1ce  jb      short loc_18003D1B2
0x18003d1d0  mov     rcx, [rbx+30h]; Block
0x18003d1d4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003d1d9  mov     rcx, [rbx+40h]; pSid
0x18003d1dd  test    rcx, rcx
0x18003d1e0  jz      short loc_18003D1EE
0x18003d1e2  call    cs:__imp_FreeSid
0x18003d1e9  nop     dword ptr [rax+rax+00h]
0x18003d1ee  mov     rcx, [rbx+8]; hMem
0x18003d1f2  test    rcx, rcx
0x18003d1f5  jz      short loc_18003D203
0x18003d1f7  call    cs:__imp_LocalFree
0x18003d1fe  nop     dword ptr [rax+rax+00h]
0x18003d203  mov     rcx, [rbx+48h]; hMem
0x18003d207  test    rcx, rcx
0x18003d20a  jz      short loc_18003D218
0x18003d20c  call    cs:__imp_LocalFree
0x18003d213  nop     dword ptr [rax+rax+00h]
0x18003d218  mov     rbx, [rsp+28h+arg_0]
0x18003d21d  add     rsp, 20h
0x18003d221  pop     rdi
0x18003d222  retn
```
