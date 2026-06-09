# CallStackContext::TraceFailure(char const *,long,long)

- ea: `0x180004778`
- end: `0x1800047fa`
- name: `?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z`
- size: `130`
- prototype: `void __fastcall(CallStackContext *__hidden this, const char *, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002160`
- `0x180003ad0`

## callees

- `0x180004778`
- `0x1800048ec`
- `0x180006010`

## pseudocode

```c
void __fastcall CallStackContext::TraceFailure(CallStackContext *this, const char *a2, unsigned int a3, int a4)
{
  const char *v8; // rax
  bool v9; // cc

  if ( (Microsoft_Windows_MediaFoundation_PlatformEnableBits & 2) != 0 )
  {
    v8 = a2;
    if ( !a2 )
      v8 = (const char *)&dword_180007A2C;
    McTemplateU0pdds_EventWriteTransfer(
      (__int64)&dword_180007A2C,
      (__int64)a2,
      (__int64)CallStackTracing::s_wpInstance,
      a3,
      a4,
      v8);
  }
  v9 = ++*((_DWORD *)this + 506) <= 0xAu;
  *((_DWORD *)this + 499) = a4;
  if ( v9 )
    (*(void (__fastcall **)(struct CallStackTracing *, CallStackContext *, const char *, _QWORD))(*(_QWORD *)CallStackTracing::s_wpInstance
                                                                                                + 16LL))(
      CallStackTracing::s_wpInstance,
      this,
      a2,
      a3);
}

```

## disassembly

```asm
0x180004778  push    rbx
0x18000477a  push    rbp
0x18000477b  push    rsi
0x18000477c  push    rdi
0x18000477d  sub     rsp, 38h
0x180004781  test    cs:Microsoft_Windows_MediaFoundation_PlatformEnableBits, 2
0x180004788  mov     esi, r9d
0x18000478b  mov     ebp, r8d
0x18000478e  mov     rdi, rdx
0x180004791  mov     rbx, rcx
0x180004794  jz      short loc_1800047C0
0x180004796  test    rdx, rdx
0x180004799  lea     rcx, dword_180007A2C
0x1800047a0  mov     rax, rdx
0x1800047a3  cmovz   rax, rcx
0x1800047a7  mov     [rsp+58h+var_30], rax
0x1800047ac  mov     [rsp+58h+var_38], r9d
0x1800047b1  mov     r9d, r8d
0x1800047b4  mov     r8, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800047bb  call    McTemplateU0pdds_EventWriteTransfer
0x1800047c0  inc     dword ptr [rbx+7E8h]
0x1800047c6  cmp     dword ptr [rbx+7E8h], 0Ah
0x1800047cd  mov     [rbx+7CCh], esi
0x1800047d3  ja      short loc_1800047F1
0x1800047d5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800047dc  mov     r9d, ebp
0x1800047df  mov     r8, rdi
0x1800047e2  mov     rdx, rbx
0x1800047e5  mov     rax, [rcx]
0x1800047e8  mov     rax, [rax+10h]
0x1800047ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047f1  add     rsp, 38h
0x1800047f5  pop     rdi
0x1800047f6  pop     rsi
0x1800047f7  pop     rbp
0x1800047f8  pop     rbx
0x1800047f9  retn
```
