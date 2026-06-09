# LogNode

- ea: `0x18002bc50`
- end: `0x18002bcd6`
- name: `LogNode`
- size: `134`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800284a0`

## callees

- `0x18002aba0`
- `0x18002bc50`
- `0x180041410`
- `0x1800439d8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002bcb9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002bcb9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002bca5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002bca5`

## string_xrefs

- `0x18002bc7e`: `xmlns:wst='http://docs.oasis-open.org/ws-sx/ws-trust/200512' xmlns:s='http://www.w3.org/2003/05/soap-envelope'`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall LogNode(struct IXMLDOMDocument2 *a1, unsigned __int16 *a2)
{
  CEnrollmentLogger *Logger; // rbx
  int NodeStringWithNamespace; // eax
  void *v6; // rbx
  HANDLE ProcessHeap; // rax
  LPVOID lpMem; // [rsp+40h] [rbp+18h] BYREF

  lpMem = 0;
  Logger = CEnrollmentLogger::GetLogger();
  NodeStringWithNamespace = HlpGetNodeStringWithNamespace(
                              a1,
                              L"xmlns:wst='http://docs.oasis-open.org/ws-sx/ws-trust/200512' xmlns:s='http://www.w3.org/20"
                               "03/05/soap-envelope'",
                              a2,
                              (unsigned __int16 **)&lpMem);
  CEnrollmentLogger::LogEnrollServerMessageParsingFound(Logger, NodeStringWithNamespace, a2);
  v6 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
  }
}

```

## disassembly

```asm
0x18002bc50  mov     [rsp+arg_0], rbx
0x18002bc55  mov     [rsp+arg_8], rsi
0x18002bc5a  push    rdi
0x18002bc5b  sub     rsp, 20h
0x18002bc5f  mov     rsi, rdx
0x18002bc62  mov     rdi, rcx
0x18002bc65  mov     [rsp+28h+lpMem], 0
0x18002bc6e  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18002bc73  mov     rbx, rax
0x18002bc76  lea     r9, [rsp+28h+lpMem]; unsigned __int16 **
0x18002bc7b  mov     r8, rsi; unsigned __int16 *
0x18002bc7e  lea     rdx, aXmlnsWstHttpDo_2; "xmlns:wst='http://docs.oasis-open.org/w"...
0x18002bc85  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x18002bc88  call    ?HlpGetNodeStringWithNamespace@@YAJPEAUIXMLDOMDocument2@@PEBG1PEAPEAG@Z; HlpGetNodeStringWithNamespace(IXMLDOMDocument2 *,ushort const *,ushort const *,ushort * *)
0x18002bc8d  mov     r8, rsi; unsigned __int16 *
0x18002bc90  mov     edx, eax; int
0x18002bc92  mov     rcx, rbx; this
0x18002bc95  call    ?LogEnrollServerMessageParsingFound@CEnrollmentLogger@@QEAAXJPEBG@Z; CEnrollmentLogger::LogEnrollServerMessageParsingFound(long,ushort const *)
0x18002bc9a  nop
0x18002bc9b  mov     rbx, [rsp+28h+lpMem]
0x18002bca0  test    rbx, rbx
0x18002bca3  jz      short loc_18002BCC5
0x18002bca5  call    cs:__imp_GetProcessHeap
0x18002bcac  nop     dword ptr [rax+rax+00h]
0x18002bcb1  mov     rcx, rax; hHeap
0x18002bcb4  mov     r8, rbx; lpMem
0x18002bcb7  xor     edx, edx; dwFlags
0x18002bcb9  call    cs:__imp_HeapFree
0x18002bcc0  nop     dword ptr [rax+rax+00h]
0x18002bcc5  mov     rbx, [rsp+28h+arg_0]
0x18002bcca  mov     rsi, [rsp+28h+arg_8]
0x18002bccf  add     rsp, 20h
0x18002bcd3  pop     rdi
0x18002bcd4  retn
```
