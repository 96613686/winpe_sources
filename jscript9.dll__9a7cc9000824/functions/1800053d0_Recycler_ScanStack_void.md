# Recycler::ScanStack(void)

- ea: `0x1800053d0`
- end: `0x18000563e`
- name: `?ScanStack@Recycler@@AEAA_KXZ`
- size: `622`
- prototype: `signed __int64 __fastcall(Recycler *this)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000618c`
- `0x1800061f8`

## callees

- `0x180004ad4`
- `0x1800053d0`
- `0x180005650`
- `0x1800057d0`
- `0x1801a31a4`
- `0x1801cc26b`
- `0x1803481f0`
- `0x180364010`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x18000542b`
- `KERNEL32!GetCurrentThread` at `0x18000542b`
- `KERNEL32!GetThreadContext` at `0x18000543f`
- `KERNEL32!GetThreadContext` at `0x18000543f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
signed __int64 __fastcall Recycler::ScanStack(Recycler *this)
{
  HANDLE CurrentThread; // rax
  unsigned __int64 i; // rcx
  void **StackBase; // rsi
  void **p_Context; // rdi
  unsigned __int64 v6; // rdx
  __int64 v8; // r9
  unsigned __int64 v9; // r10
  __int64 v10; // r8
  CONTEXT Context; // [rsp+20h] [rbp-508h] BYREF

  if ( *((_BYTE *)this + 12906) )
    return 0;
  if ( (Microsoft_JScriptEnableBits & 0x20) != 0 )
    McTemplateU0p_EventWriteTransfer(this, JSCRIPT_GC_SCANSTACK_START, this);
  memset_0(&Context, 0, sizeof(Context));
  Context.ContextFlags = 1048578;
  CurrentThread = GetCurrentThread();
  if ( !GetThreadContext(CurrentThread, &Context) )
  {
    Js::Throw::FatalInternalError();
    __debugbreak();
  }
  StackBase = (void **)NtCurrentTeb()->NtTib.StackBase;
  if ( &Context < (CONTEXT *)StackBase )
  {
    p_Context = (void **)&Context;
    if ( *((_BYTE *)this + 12896) )
    {
      do
      {
        if ( *p_Context )
        {
          v6 = (unsigned __int64)*p_Context & 0xFFFFFFFFFFFFFFE0uLL;
          if ( v6 >= 0x10000 )
          {
            for ( i = *((_QWORD *)this + 45); i; i = *(_QWORD *)(i + 8) )
            {
              if ( *(_DWORD *)i == HIDWORD(v6) )
              {
                i = *(_QWORD *)(i + 8 * ((unsigned __int64)(unsigned int)v6 >> 20) + 24);
                if ( i )
                  i = *(_QWORD *)(i + 8LL * (unsigned __int8)((unsigned __int64)(unsigned int)v6 >> 12) + 8);
                if ( i )
                  (*(void (__fastcall **)(unsigned __int64, unsigned __int64, Recycler *))(*(_QWORD *)i + 24LL))(
                    i,
                    v6,
                    this);
                break;
              }
            }
          }
        }
        ++p_Context;
      }
      while ( p_Context < StackBase );
    }
    else
    {
      do
      {
        if ( (unsigned __int64)*p_Context >= 0x10000 && (*(_BYTE *)p_Context & 0x1F) == 0 )
        {
          for ( i = *((_QWORD *)this + 45); i; i = *(_QWORD *)(i + 8) )
          {
            if ( *(_DWORD *)i == (unsigned __int64)*p_Context >> 32 )
            {
              v8 = *(_QWORD *)(i + 8 * ((unsigned __int64)*(unsigned int *)p_Context >> 20) + 24);
              if ( v8 )
                v8 = *(_QWORD *)(v8 + 8LL * (unsigned __int8)((unsigned __int64)*(unsigned int *)p_Context >> 12) + 8);
              if ( v8 )
              {
                switch ( *(_BYTE *)(v8 + 24) )
                {
                  case 0:
                  case 1:
                    SmallNormalHeapBlock::Mark((SmallNormalHeapBlock *)v8, *p_Context, this);
                    break;
                  case 2:
                    v9 = (unsigned __int64)((*(unsigned __int16 *)p_Context >> 5) & 0x7F) >> 6;
                    i = (*(unsigned __int16 *)p_Context >> 5) & 0x3F;
                    v10 = *(_QWORD *)(v8 + 8 * v9 + 88);
                    if ( !_bittest64(&v10, i) )
                    {
                      _bittestandset64(&v10, (*(unsigned __int16 *)p_Context >> 5) & 0x3F);
                      *(_QWORD *)(v8 + 8 * v9 + 88) = v10;
                      ++*(_WORD *)(v8 + 80);
                    }
                    break;
                  case 3:
                    LargeHeapBlock::Mark((LargeHeapBlock *)v8, *p_Context, this);
                    break;
                }
              }
              break;
            }
          }
        }
        ++p_Context;
      }
      while ( p_Context < StackBase );
    }
  }
  if ( (Microsoft_JScriptEnableBits & 0x20) != 0 )
    McTemplateU0p_EventWriteTransfer(i, JSCRIPT_GC_SCANSTACK_STOP, this);
  return (char *)StackBase - (char *)&Context;
}

```

## disassembly

```asm
0x1800053d0  mov     r11, rsp
0x1800053d3  mov     [r11+8], rcx
0x1800053d7  push    rbx
0x1800053d8  push    rbp
0x1800053d9  push    rsi
0x1800053da  push    rdi
0x1800053db  sub     rsp, 508h
0x1800053e2  mov     rax, cs:__security_cookie
0x1800053e9  xor     rax, rsp
0x1800053ec  mov     [rsp+528h+var_38], rax
0x1800053f4  cmp     byte ptr [rcx+326Ah], 0
0x1800053fb  mov     rbx, rcx
0x1800053fe  jnz     loc_180005529
0x180005404  test    byte ptr cs:Microsoft_JScriptEnableBits, 20h
0x18000540b  jnz     loc_18000561A
0x180005411  xor     edx, edx; Val
0x180005413  lea     rcx, [rsp+528h+Context]; void *
0x180005418  mov     r8d, 4D0h; Size
0x18000541e  call    memset_0
0x180005423  mov     [rsp+528h+Context.ContextFlags], 100002h
0x18000542b  call    cs:__imp_GetCurrentThread
0x180005432  nop     dword ptr [rax+rax+00h]
0x180005437  mov     rcx, rax; hThread
0x18000543a  lea     rdx, [rsp+528h+Context]; lpContext
0x18000543f  call    cs:__imp_GetThreadContext
0x180005446  nop     dword ptr [rax+rax+00h]
0x18000544b  test    eax, eax
0x18000544d  jz      loc_18000562E
0x180005453  mov     rax, gs:30h
0x18000545c  mov     rsi, [rax+8]
0x180005460  lea     rax, [rsp+528h+Context]
0x180005465  mov     rbp, rsi
0x180005468  sub     rbp, rax
0x18000546b  lea     rax, [rsp+528h+Context]
0x180005470  cmp     rax, rsi
0x180005473  jnb     short loc_1800054E5
0x180005475  cmp     byte ptr [rbx+3260h], 0
0x18000547c  lea     rdi, [rsp+528h+Context]
0x180005481  jz      loc_18000552D
0x180005487  mov     rdx, [rdi]
0x18000548a  test    rdx, rdx
0x18000548d  jz      short loc_1800054DC
0x18000548f  and     rdx, 0FFFFFFFFFFFFFFE0h
0x180005493  cmp     rdx, 10000h
0x18000549a  jb      short loc_1800054DC
0x18000549c  mov     rcx, [rbx+168h]
0x1800054a3  mov     rax, rdx
0x1800054a6  shr     rax, 20h
0x1800054aa  test    rcx, rcx
0x1800054ad  jz      short loc_1800054DC
0x1800054af  cmp     [rcx], eax
0x1800054b1  jnz     short loc_180005512
0x1800054b3  mov     eax, edx
0x1800054b5  shr     rax, 14h
0x1800054b9  mov     r8d, edx
0x1800054bc  mov     rcx, [rcx+rax*8+18h]
0x1800054c1  test    rcx, rcx
0x1800054c4  jz      loc_180005639
0x1800054ca  shr     r8, 0Ch
0x1800054ce  movzx   eax, r8b
0x1800054d2  mov     rcx, [rcx+rax*8+8]
0x1800054d7  test    rcx, rcx
0x1800054da  jnz     short loc_180005518
0x1800054dc  add     rdi, 8
0x1800054e0  cmp     rdi, rsi
0x1800054e3  jb      short loc_180005487
0x1800054e5  test    byte ptr cs:Microsoft_JScriptEnableBits, 20h
0x1800054ec  jnz     loc_180005606
0x1800054f2  mov     rax, rbp
0x1800054f5  mov     rcx, [rsp+528h+var_38]
0x1800054fd  xor     rcx, rsp; StackCookie
0x180005500  call    __security_check_cookie
0x180005505  add     rsp, 508h
0x18000550c  pop     rdi
0x18000550d  pop     rsi
0x18000550e  pop     rbp
0x18000550f  pop     rbx
0x180005510  retn
0x180005512  mov     rcx, [rcx+8]
0x180005516  jmp     short loc_1800054AA
0x180005518  mov     rax, [rcx]
0x18000551b  mov     r8, rbx
0x18000551e  mov     rax, [rax+18h]
0x180005522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005527  jmp     short loc_1800054DC
0x180005529  xor     eax, eax
0x18000552b  jmp     short loc_1800054F5
0x18000552d  cmp     qword ptr [rdi], 10000h
0x180005534  jb      short loc_18000553B
0x180005536  test    byte ptr [rdi], 1Fh
0x180005539  jz      short loc_180005546
0x18000553b  add     rdi, 8
0x18000553f  cmp     rdi, rsi
0x180005542  jb      short loc_18000552D
0x180005544  jmp     short loc_1800054E5
0x180005546  mov     rax, [rdi]
0x180005549  mov     rcx, [rbx+168h]
0x180005550  shr     rax, 20h
0x180005554  test    rcx, rcx
0x180005557  jz      short loc_18000553B
0x180005559  cmp     [rcx], eax
0x18000555b  jnz     short loc_1800055B0
0x18000555d  mov     edx, [rdi]
0x18000555f  mov     eax, edx
0x180005561  shr     rax, 14h
0x180005565  mov     r9, [rcx+rax*8+18h]
0x18000556a  test    r9, r9
0x18000556d  jz      loc_180005634
0x180005573  shr     rdx, 0Ch
0x180005577  movzx   eax, dl
0x18000557a  mov     r9, [r9+rax*8+8]
0x18000557f  test    r9, r9
0x180005582  jz      short loc_18000553B
0x180005584  movzx   r8d, byte ptr [r9+18h]
0x180005589  test    r8d, r8d
0x18000558c  jz      short loc_1800055B6
0x18000558e  sub     r8d, 1
0x180005592  jz      short loc_1800055B6
0x180005594  sub     r8d, 1
0x180005598  jz      short loc_1800055C9
0x18000559a  cmp     r8d, 1
0x18000559e  jnz     short loc_18000553B
0x1800055a0  mov     rdx, [rdi]; void *
0x1800055a3  mov     r8, rbx; struct Recycler *
0x1800055a6  mov     rcx, r9; this
0x1800055a9  call    ?Mark@LargeHeapBlock@@QEAAXPEAXPEAVRecycler@@@Z; LargeHeapBlock::Mark(void *,Recycler *)
0x1800055ae  jmp     short loc_18000553B
0x1800055b0  mov     rcx, [rcx+8]
0x1800055b4  jmp     short loc_180005554
0x1800055b6  mov     rdx, [rdi]; void *
0x1800055b9  mov     r8, rbx; struct Recycler *
0x1800055bc  mov     rcx, r9; this
0x1800055bf  call    ?Mark@SmallNormalHeapBlock@@QEAAXPEAXPEAVRecycler@@@Z; SmallNormalHeapBlock::Mark(void *,Recycler *)
0x1800055c4  jmp     loc_18000553B
0x1800055c9  movzx   eax, word ptr [rdi]
0x1800055cc  shr     eax, 5
0x1800055cf  and     eax, 7Fh
0x1800055d2  mov     r10d, eax
0x1800055d5  shr     r10, 6
0x1800055d9  mov     edx, eax
0x1800055db  and     eax, 3Fh
0x1800055de  movzx   ecx, al
0x1800055e1  mov     r8, [r9+r10*8+58h]
0x1800055e6  bt      r8, rcx
0x1800055ea  jb      loc_18000553B
0x1800055f0  and     edx, 3Fh
0x1800055f3  bts     r8, rdx
0x1800055f7  mov     [r9+r10*8+58h], r8
0x1800055fc  inc     word ptr [r9+50h]
0x180005601  jmp     loc_18000553B
0x180005606  mov     r8, rbx
0x180005609  lea     rdx, JSCRIPT_GC_SCANSTACK_STOP
0x180005610  call    McTemplateU0p_EventWriteTransfer
0x180005615  jmp     loc_1800054F2
0x18000561a  mov     r8, rbx
0x18000561d  lea     rdx, JSCRIPT_GC_SCANSTACK_START
0x180005624  call    McTemplateU0p_EventWriteTransfer
0x180005629  jmp     loc_180005411
0x18000562e  call    ?FatalInternalError@Throw@Js@@SAXXZ; Js::Throw::FatalInternalError(void)
0x180005633  int     3; Trap to Debugger
0x180005634  jmp     loc_18000557F
0x180005639  jmp     loc_1800054D7
```
