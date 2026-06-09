# ProcessToken::~ProcessToken(void)

- ea: `0x18002ee18`
- end: `0x18002eedc`
- name: `??1ProcessToken@@QEAA@XZ`
- size: `196`
- prototype: `void __fastcall(ProcessToken *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800d7980`

## callees

- `0x18002ee18`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ee5d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ee92`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ee5d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ee92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ee73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002eea9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002eec3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ee73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002eea9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002eec3`

## pseudocode

```c
void __fastcall ProcessToken::~ProcessToken(ProcessToken *this)
{
  void *pPackageSid; // r8

  if ( this->_pSelfSid )
  {
    HeapFree(g_hHeap, 0, this->_pSelfSid);
    this->_pSelfSid = 0;
  }
  if ( this->_stringSelfSid )
  {
    WindowsDeleteString(this->_stringSelfSid);
    this->_stringSelfSid = 0;
  }
  pPackageSid = this->_pPackageSid;
  if ( pPackageSid )
  {
    HeapFree(g_hHeap, 0, pPackageSid);
    this->_pPackageSid = 0;
  }
  if ( this->_stringPackageSid )
  {
    WindowsDeleteString(this->_stringPackageSid);
    this->_stringPackageSid = 0;
  }
  if ( this->_packageMoniker )
  {
    WindowsDeleteString(this->_packageMoniker);
    this->_packageMoniker = 0;
  }
}

```

## disassembly

```asm
0x18002ee18  push    rbx
0x18002ee1a  sub     rsp, 20h
0x18002ee1e  mov     r8, [this]; lpMem
0x18002ee21  mov     rbx, this
0x18002ee24  test    r8, r8
0x18002ee27  jnz     short loc_18002EE54
0x18002ee29  mov     rax, [rbx+8]
0x18002ee2d  test    rax, rax
0x18002ee30  jnz     short loc_18002EE6F
0x18002ee32  mov     r8, [rbx+10h]; lpMem
0x18002ee36  test    r8, r8
0x18002ee39  jnz     short loc_18002EE89
0x18002ee3b  mov     rax, [rbx+18h]
0x18002ee3f  test    rax, rax
0x18002ee42  jnz     short loc_18002EEA5
0x18002ee44  mov     rax, [rbx+20h]
0x18002ee48  test    rax, rax
0x18002ee4b  jnz     short loc_18002EEBF
0x18002ee4d  add     rsp, 20h
0x18002ee51  pop     rbx
0x18002ee52  retn
0x18002ee54  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x18002ee5b  xor     edx, edx; dwFlags
0x18002ee5d  call    cs:__imp_HeapFree
0x18002ee64  nop     dword ptr [rax+rax+00h]
0x18002ee69  and     qword ptr [rbx], 0
0x18002ee6d  jmp     short loc_18002EE29
0x18002ee6f  mov     this, [rbx+8]; string
0x18002ee73  call    cs:__imp_WindowsDeleteString
0x18002ee7a  nop     dword ptr [rax+rax+00h]
0x18002ee7f  mov     qword ptr [rbx+8], 0
0x18002ee87  jmp     short loc_18002EE32
0x18002ee89  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x18002ee90  xor     edx, edx; dwFlags
0x18002ee92  call    cs:__imp_HeapFree
0x18002ee99  nop     dword ptr [rax+rax+00h]
0x18002ee9e  and     qword ptr [rbx+10h], 0
0x18002eea3  jmp     short loc_18002EE3B
0x18002eea5  mov     this, [rbx+18h]; string
0x18002eea9  call    cs:__imp_WindowsDeleteString
0x18002eeb0  nop     dword ptr [rax+rax+00h]
0x18002eeb5  mov     qword ptr [rbx+18h], 0
0x18002eebd  jmp     short loc_18002EE44
0x18002eebf  mov     this, [rbx+20h]; string
0x18002eec3  call    cs:__imp_WindowsDeleteString
0x18002eeca  nop     dword ptr [rax+rax+00h]
0x18002eecf  mov     qword ptr [rbx+20h], 0
0x18002eed7  jmp     loc_18002EE4D
```
