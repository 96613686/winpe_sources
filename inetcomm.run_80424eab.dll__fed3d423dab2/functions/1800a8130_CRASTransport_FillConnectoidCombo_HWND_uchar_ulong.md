# CRASTransport::FillConnectoidCombo(HWND__ *,uchar,ulong *)

- ea: `0x1800a8130`
- end: `0x1800a8194`
- name: `?FillConnectoidCombo@CRASTransport@@UEAAJPEAUHWND__@@EPEAK@Z`
- size: `100`
- prototype: `int(CRASTransport *__hidden this, HWND, unsigned __int8, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800a8130`

## import_xrefs

- `MSOERT2!HrFillRasCombo` at `0x1800a816d`
- `MSOERT2!HrFillRasCombo` at `0x1800a816d`
- `KERNEL32!LeaveCriticalSection` at `0x1800a817c`
- `KERNEL32!LeaveCriticalSection` at `0x1800a817c`
- `KERNEL32!EnterCriticalSection` at `0x1800a815f`
- `KERNEL32!EnterCriticalSection` at `0x1800a815f`
- `USER32!IsWindow` at `0x1800a814e`
- `USER32!IsWindow` at `0x1800a814e`

## pseudocode

```c
__int64 __fastcall CRASTransport::FillConnectoidCombo(
        CRASTransport *this,
        HWND a2,
        unsigned __int8 a3,
        unsigned int *a4)
{
  unsigned int v4; // ebp
  unsigned int v8; // ebx

  v4 = a3;
  if ( !a2 || !IsWindow(a2) )
    return 2147942487LL;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 2688));
  v8 = HrFillRasCombo(a2, v4, a4);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 2688));
  return v8;
}

```

## disassembly

```asm
0x1800a8130  push    rbx
0x1800a8132  push    rbp
0x1800a8133  push    rsi
0x1800a8134  push    rdi
0x1800a8135  sub     rsp, 28h
0x1800a8139  movzx   ebp, r8b
0x1800a813d  mov     rsi, r9
0x1800a8140  mov     rbx, rdx
0x1800a8143  mov     rdi, rcx
0x1800a8146  test    rdx, rdx
0x1800a8149  jz      short loc_1800A8186
0x1800a814b  mov     rcx, rdx; hWnd
0x1800a814e  call    cs:__imp_IsWindow
0x1800a8154  test    eax, eax
0x1800a8156  jz      short loc_1800A8186
0x1800a8158  lea     rcx, [rdi+0A80h]; lpCriticalSection
0x1800a815f  call    cs:__imp_EnterCriticalSection
0x1800a8165  mov     edx, ebp
0x1800a8167  mov     r8, rsi
0x1800a816a  mov     rcx, rbx
0x1800a816d  call    cs:__imp_HrFillRasCombo
0x1800a8173  mov     ebx, eax
0x1800a8175  lea     rcx, [rdi+0A80h]; lpCriticalSection
0x1800a817c  call    cs:__imp_LeaveCriticalSection
0x1800a8182  mov     eax, ebx
0x1800a8184  jmp     short loc_1800A818B
0x1800a8186  mov     eax, 80070057h
0x1800a818b  add     rsp, 28h
0x1800a818f  pop     rdi
0x1800a8190  pop     rsi
0x1800a8191  pop     rbp
0x1800a8192  pop     rbx
0x1800a8193  retn
```
