# CUmRdp::~CUmRdp(void)

- ea: `0x140016a8c`
- end: `0x140016b10`
- name: `??1CUmRdp@@IEAA@XZ`
- size: `132`
- prototype: `void __fastcall(CUmRdp *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140015c20`

## callees

- `0x1400028f4`
- `0x140016a8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140016aeb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140016aeb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016afa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016afa`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140016aa7`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140016aa7`
- `MPR!WNetCancelConnection2W` at `0x140016ac3`
- `MPR!WNetCancelConnection2W` at `0x140016ac3`

## pseudocode

```c
void __fastcall CUmRdp::~CUmRdp(CUmRdp *this)
{
  void *v2; // rcx
  void **v3; // rsi
  _QWORD *v4; // rax
  __int64 v5; // rdx
  WCHAR *v6; // rdi
  void *v7; // rcx

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
    FreeSid(v2);
  if ( *((_DWORD *)this + 7) )
  {
    v3 = (void **)((char *)this + 72);
    while ( 1 )
    {
      v6 = (WCHAR *)*v3;
      if ( *v3 == v3 )
        break;
      WNetCancelConnection2W(v6 + 8, 0, 1);
      v4 = (_QWORD *)*((_QWORD *)v6 + 1);
      v5 = *(_QWORD *)v6;
      *v4 = *(_QWORD *)v6;
      *(_QWORD *)(v5 + 8) = v4;
      operator delete(v6);
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  }
  v7 = (void *)*((_QWORD *)this + 2);
  if ( v7 )
    CloseHandle(v7);
}

```

## disassembly

```asm
0x140016a8c  mov     [rsp+arg_0], rbx
0x140016a91  mov     [rsp+arg_8], rsi
0x140016a96  push    rdi
0x140016a97  sub     rsp, 20h
0x140016a9b  mov     rbx, rcx
0x140016a9e  mov     rcx, [rcx+8]; pSid
0x140016aa2  test    rcx, rcx
0x140016aa5  jz      short loc_140016AAD
0x140016aa7  call    cs:__imp_FreeSid
0x140016aad  cmp     dword ptr [rbx+1Ch], 0
0x140016ab1  jz      short loc_140016AF1
0x140016ab3  lea     rsi, [rbx+48h]
0x140016ab7  jmp     short loc_140016ADF
0x140016ab9  xor     edx, edx; dwFlags
0x140016abb  lea     rcx, [rdi+10h]; lpName
0x140016abf  lea     r8d, [rdx+1]; fForce
0x140016ac3  call    cs:__imp_WNetCancelConnection2W
0x140016ac9  mov     rax, [rdi+8]
0x140016acd  mov     rcx, rdi; Block
0x140016ad0  mov     rdx, [rdi]
0x140016ad3  mov     [rax], rdx
0x140016ad6  mov     [rdx+8], rax
0x140016ada  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140016adf  mov     rdi, [rsi]
0x140016ae2  cmp     rdi, rsi
0x140016ae5  jnz     short loc_140016AB9
0x140016ae7  lea     rcx, [rbx+20h]; lpCriticalSection
0x140016aeb  call    cs:__imp_DeleteCriticalSection
0x140016af1  mov     rcx, [rbx+10h]; hObject
0x140016af5  test    rcx, rcx
0x140016af8  jz      short loc_140016B00
0x140016afa  call    cs:__imp_CloseHandle
0x140016b00  mov     rbx, [rsp+28h+arg_0]
0x140016b05  mov     rsi, [rsp+28h+arg_8]
0x140016b0a  add     rsp, 20h
0x140016b0e  pop     rdi
0x140016b0f  retn
```
