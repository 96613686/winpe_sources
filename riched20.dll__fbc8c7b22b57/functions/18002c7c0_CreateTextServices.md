# CreateTextServices

- ea: `0x18002c7c0`
- end: `0x18002c8f8`
- name: `CreateTextServices`
- size: `312`
- prototype: `__int64 __fastcall(struct IUnknown *, struct ITextHost2 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x1800616e8`

## callees

- `0x18002b0dc`
- `0x18002c7c0`
- `0x18003fd98`
- `0x1800418f8`
- `0x180042bf8`
- `0x18004e34c`
- `0x18005cc50`
- `0x180060eac`
- `0x1800610b0`
- `0x180091984`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18002c7e8`
- `KERNEL32!EnterCriticalSection` at `0x18002c7e8`
- `KERNEL32!LeaveCriticalSection` at `0x18002c82a`
- `KERNEL32!LeaveCriticalSection` at `0x18002c84c`
- `KERNEL32!LeaveCriticalSection` at `0x18002c82a`
- `KERNEL32!LeaveCriticalSection` at `0x18002c84c`
- `KERNEL32!GetProcessHeap` at `0x18002c86e`
- `KERNEL32!GetProcessHeap` at `0x18002c86e`
- `KERNEL32!HeapAlloc` at `0x18002c894`
- `KERNEL32!HeapAlloc` at `0x18002c894`

## pseudocode

```c
__int64 __fastcall CreateTextServices(struct IUnknown *a1, struct ITextHost2 *a2, _QWORD *a3)
{
  HANDLE ProcessHeap; // rax
  CTxtEdit *v8; // rax
  CTxtEdit *v9; // rax
  const struct tagRECT *v10; // rdx
  CTxtEdit *v11; // rbx
  unsigned int v12; // edx

  if ( !byte_1800A7548 )
  {
    EnterCriticalSection(&g_CriticalSection);
    byte_1800A7548 = 1;
    CW32System::InitSysParams(0);
    CW32System::InitPreferredFontInfo();
    RegisterFETCs();
    if ( (int)CreateFormatCaches() < 0 || !(unsigned int)InitKinsokuClassify() )
    {
      LeaveCriticalSection(&g_CriticalSection);
      return 2147500037LL;
    }
    InitFontCache();
    LeaveCriticalSection(&g_CriticalSection);
  }
  if ( !a3 )
    return 2147942487LL;
  ProcessHeap = g_hHeap;
  if ( g_hHeap || (ProcessHeap = GetProcessHeap(), (g_hHeap = ProcessHeap) != 0) )
  {
    v8 = (CTxtEdit *)HeapAlloc(ProcessHeap, 8u, 0x138u);
    if ( v8 )
    {
      v9 = CTxtEdit::CTxtEdit(v8, a2, a1);
      v11 = v9;
      if ( v9 )
      {
        if ( (unsigned int)CTxtEdit::Init(v9, v10) )
        {
          *a3 = (char *)v11 + 232;
          return 0;
        }
        CTxtEdit::`scalar deleting destructor'(v11, v12);
        return 2147500037LL;
      }
    }
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18002c7c0  mov     [rsp+arg_0], rbx
0x18002c7c5  mov     [rsp+arg_8], rsi
0x18002c7ca  push    rdi
0x18002c7cb  sub     rsp, 20h
0x18002c7cf  cmp     cs:byte_1800A7548, 0
0x18002c7d6  mov     rdi, r8
0x18002c7d9  mov     rbx, rdx
0x18002c7dc  mov     rsi, rcx
0x18002c7df  jnz     short loc_18002C836
0x18002c7e1  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002c7e8  call    cs:__imp_EnterCriticalSection
0x18002c7ef  nop     dword ptr [rax+rax+00h]
0x18002c7f4  xor     ecx, ecx; int
0x18002c7f6  mov     cs:byte_1800A7548, 1
0x18002c7fd  call    ?InitSysParams@CW32System@@SAXH@Z; CW32System::InitSysParams(int)
0x18002c802  call    ?InitPreferredFontInfo@CW32System@@SAXXZ; CW32System::InitPreferredFontInfo(void)
0x18002c807  call    ?RegisterFETCs@@YAXXZ; RegisterFETCs(void)
0x18002c80c  call    ?CreateFormatCaches@@YAJXZ; CreateFormatCaches(void)
0x18002c811  test    eax, eax
0x18002c813  js      short loc_18002C845
0x18002c815  call    ?InitKinsokuClassify@@YAHXZ; InitKinsokuClassify(void)
0x18002c81a  test    eax, eax
0x18002c81c  jz      short loc_18002C845
0x18002c81e  call    ?InitFontCache@@YAXXZ; InitFontCache(void)
0x18002c823  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002c82a  call    cs:__imp_LeaveCriticalSection
0x18002c831  nop     dword ptr [rax+rax+00h]
0x18002c836  test    rdi, rdi
0x18002c839  jnz     short loc_18002C862
0x18002c83b  mov     eax, 80070057h
0x18002c840  jmp     loc_18002C8E7
0x18002c845  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002c84c  call    cs:__imp_LeaveCriticalSection
0x18002c853  nop     dword ptr [rax+rax+00h]
0x18002c858  mov     eax, 80004005h
0x18002c85d  jmp     loc_18002C8E7
0x18002c862  mov     rax, cs:?g_hHeap@@3PEAXEA; void * g_hHeap
0x18002c869  test    rax, rax
0x18002c86c  jnz     short loc_18002C886
0x18002c86e  call    cs:__imp_GetProcessHeap
0x18002c875  nop     dword ptr [rax+rax+00h]
0x18002c87a  mov     cs:?g_hHeap@@3PEAXEA, rax; void * g_hHeap
0x18002c881  test    rax, rax
0x18002c884  jz      short loc_18002C8E2
0x18002c886  mov     edx, 8; dwFlags
0x18002c88b  mov     r8d, 138h; dwBytes
0x18002c891  mov     rcx, rax; hHeap
0x18002c894  call    cs:__imp_HeapAlloc
0x18002c89b  nop     dword ptr [rax+rax+00h]
0x18002c8a0  test    rax, rax
0x18002c8a3  jz      short loc_18002C8E2
0x18002c8a5  mov     r8, rsi; struct IUnknown *
0x18002c8a8  mov     rdx, rbx; struct ITextHost2 *
0x18002c8ab  mov     rcx, rax; this
0x18002c8ae  call    ??0CTxtEdit@@QEAA@PEAVITextHost2@@PEAUIUnknown@@@Z; CTxtEdit::CTxtEdit(ITextHost2 *,IUnknown *)
0x18002c8b3  mov     rbx, rax
0x18002c8b6  test    rax, rax
0x18002c8b9  jz      short loc_18002C8E2
0x18002c8bb  mov     rcx, rax; this
0x18002c8be  call    ?Init@CTxtEdit@@QEAAHPEBUtagRECT@@@Z; CTxtEdit::Init(tagRECT const *)
0x18002c8c3  test    eax, eax
0x18002c8c5  jz      short loc_18002C8D5
0x18002c8c7  lea     rax, [rbx+0E8h]
0x18002c8ce  mov     [rdi], rax
0x18002c8d1  xor     eax, eax
0x18002c8d3  jmp     short loc_18002C8E7
0x18002c8d5  mov     rcx, rbx; this
0x18002c8d8  call    ??_GCTxtEdit@@QEAAPEAXI@Z; CTxtEdit::`scalar deleting destructor'(uint)
0x18002c8dd  jmp     loc_18002C858
0x18002c8e2  mov     eax, 8007000Eh
0x18002c8e7  mov     rbx, [rsp+28h+arg_0]
0x18002c8ec  mov     rsi, [rsp+28h+arg_8]
0x18002c8f1  add     rsp, 20h
0x18002c8f5  pop     rdi
0x18002c8f6  retn
```
