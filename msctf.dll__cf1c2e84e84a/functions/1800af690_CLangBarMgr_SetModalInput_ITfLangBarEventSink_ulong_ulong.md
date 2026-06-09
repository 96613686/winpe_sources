# CLangBarMgr::SetModalInput(ITfLangBarEventSink *,ulong,ulong)

- ea: `0x1800af690`
- end: `0x1800af74d`
- name: `?SetModalInput@CLangBarMgr@@UEAAJPEAUITfLangBarEventSink@@KK@Z`
- size: `189`
- prototype: `int(CLangBarMgr *__hidden this, struct ITfLangBarEventSink *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18003f2f0`
- `0x1800af690`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800af6a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800af6a9`
- `USER32!PostThreadMessageW` at `0x1800af6f8`
- `USER32!PostThreadMessageW` at `0x1800af724`
- `USER32!PostThreadMessageW` at `0x1800af738`
- `USER32!PostThreadMessageW` at `0x1800af6f8`
- `USER32!PostThreadMessageW` at `0x1800af724`
- `USER32!PostThreadMessageW` at `0x1800af738`

## pseudocode

```c
__int64 __fastcall CLangBarMgr::SetModalInput(CLangBarMgr *this, struct IUnknown *a2, DWORD a3, int a4)
{
  DWORD CurrentThreadId; // eax
  LPARAM v9; // rdi
  unsigned int v10; // ebx

  CurrentThreadId = GetCurrentThreadId();
  v9 = CurrentThreadId;
  if ( a2 )
    v10 = ((a4 >> 31) & 0x18) + 8;
  else
    v10 = 9;
  if ( !a3 )
    return 2147500037LL;
  if ( *((_QWORD *)this + 9) )
  {
    if ( a2 )
      PostThreadMessageW(*((_DWORD *)this + 16), g_msgPrivate, 9u, CurrentThreadId);
    goto LABEL_11;
  }
  if ( a2 )
  {
LABEL_11:
    if ( *((struct IUnknown **)this + 9) != a2 )
      ATL::AtlComPtrAssign((struct IUnknown **)this + 9, a2);
    *((_DWORD *)this + 16) = a3;
    if ( a3 != (_DWORD)v9 )
      PostThreadMessageW(a3, g_msgPrivate, v10, v9);
    PostThreadMessageW(v9, g_msgPrivate, v10, v9);
  }
  return 0;
}

```

## disassembly

```asm
0x1800af690  push    rbx
0x1800af692  push    rbp
0x1800af693  push    rsi
0x1800af694  push    rdi
0x1800af695  push    r14
0x1800af697  push    r15
0x1800af699  sub     rsp, 28h
0x1800af69d  mov     ebx, r9d
0x1800af6a0  mov     esi, r8d
0x1800af6a3  mov     rbp, rdx
0x1800af6a6  mov     r15, rcx
0x1800af6a9  call    cs:__imp_GetCurrentThreadId
0x1800af6af  mov     edi, eax
0x1800af6b1  mov     r8d, 9; wParam
0x1800af6b7  test    rbp, rbp
0x1800af6ba  jz      short loc_1800AF6C7
0x1800af6bc  sar     ebx, 1Fh
0x1800af6bf  and     ebx, 18h
0x1800af6c2  add     ebx, 8
0x1800af6c5  jmp     short loc_1800AF6CA
0x1800af6c7  mov     ebx, r8d
0x1800af6ca  test    esi, esi
0x1800af6cc  jnz     short loc_1800AF6D5
0x1800af6ce  mov     eax, 80004005h
0x1800af6d3  jmp     short loc_1800AF740
0x1800af6d5  lea     r14, [r15+48h]
0x1800af6d9  cmp     qword ptr [r14], 0
0x1800af6dd  jnz     short loc_1800AF6E6
0x1800af6df  test    rbp, rbp
0x1800af6e2  jnz     short loc_1800AF6FE
0x1800af6e4  jmp     short loc_1800AF73E
0x1800af6e6  test    rbp, rbp
0x1800af6e9  jz      short loc_1800AF6FE
0x1800af6eb  mov     edx, cs:?g_msgPrivate@@3IA; Msg
0x1800af6f1  mov     r9, rdi; lParam
0x1800af6f4  mov     ecx, [r15+40h]; idThread
0x1800af6f8  call    cs:__imp_PostThreadMessageW
0x1800af6fe  cmp     [r14], rbp
0x1800af701  jz      short loc_1800AF70E
0x1800af703  mov     rdx, rbp; struct IUnknown *
0x1800af706  mov     rcx, r14; struct IUnknown **
0x1800af709  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800af70e  mov     [r15+40h], esi
0x1800af712  cmp     esi, edi
0x1800af714  jz      short loc_1800AF72A
0x1800af716  mov     edx, cs:?g_msgPrivate@@3IA; Msg
0x1800af71c  mov     r9, rdi; lParam
0x1800af71f  mov     r8d, ebx; wParam
0x1800af722  mov     ecx, esi; idThread
0x1800af724  call    cs:__imp_PostThreadMessageW
0x1800af72a  mov     edx, cs:?g_msgPrivate@@3IA; Msg
0x1800af730  mov     r9, rdi; lParam
0x1800af733  mov     r8d, ebx; wParam
0x1800af736  mov     ecx, edi; idThread
0x1800af738  call    cs:__imp_PostThreadMessageW
0x1800af73e  xor     eax, eax
0x1800af740  add     rsp, 28h
0x1800af744  pop     r15
0x1800af746  pop     r14
0x1800af748  pop     rdi
0x1800af749  pop     rsi
0x1800af74a  pop     rbp
0x1800af74b  pop     rbx
0x1800af74c  retn
```
