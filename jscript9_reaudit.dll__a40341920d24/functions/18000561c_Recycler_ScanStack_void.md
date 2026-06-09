# Recycler::ScanStack(void)

- ea: `0x18000561c`
- end: `0x18000587d`
- name: `?ScanStack@Recycler@@AEAA_KXZ`
- size: `609`
- prototype: `unsigned __int64 __fastcall(Recycler *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180006790`
- `0x180007f6c`

## callees

- `0x18000463c`
- `0x18000561c`
- `0x180005890`
- `0x180005a10`
- `0x1801a0e70`
- `0x1801c989b`
- `0x180341dd0`
- `0x18035e010`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180005677`
- `KERNEL32!GetCurrentThread` at `0x180005677`
- `KERNEL32!GetThreadContext` at `0x180005685`
- `KERNEL32!GetThreadContext` at `0x180005685`

## pseudocode

```c
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
    McTemplateU0p_EventWriteTransfer(this, &JSCRIPT_GC_SCANSTACK_START, this);
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
    McTemplateU0p_EventWriteTransfer(i, &JSCRIPT_GC_SCANSTACK_STOP, this);
  return (char *)StackBase - (char *)&Context;
}

```

## disassembly

```asm
0x18000561c  mov     r11, rsp
0x18000561f  mov     [r11+8], rcx
0x180005623  push    rbx
0x180005624  push    rbp
0x180005625  push    rsi
0x180005626  push    rdi
0x180005627  sub     rsp, 508h
0x18000562e  mov     rax, cs:__security_cookie
0x180005635  xor     rax, rsp
0x180005638  mov     [rsp+528h+var_38], rax
0x180005640  cmp     byte ptr [rcx+326Ah], 0
0x180005647  mov     rbx, rcx
0x18000564a  jnz     loc_180005768
0x180005650  test    byte ptr cs:Microsoft_JScriptEnableBits, 20h
0x180005657  jnz     loc_180005859
0x18000565d  xor     edx, edx; Val
0x18000565f  lea     rcx, [rsp+528h+Context]; void *
0x180005664  mov     r8d, 4D0h; Size
0x18000566a  call    memset_0
0x18000566f  mov     [rsp+528h+Context.ContextFlags], 100002h
0x180005677  call    cs:__imp_GetCurrentThread
0x18000567d  mov     rcx, rax; hThread
0x180005680  lea     rdx, [rsp+528h+Context]; lpContext
0x180005685  call    cs:__imp_GetThreadContext
0x18000568b  test    eax, eax
0x18000568d  jz      loc_18000586D
0x180005693  mov     rax, gs:30h
0x18000569c  mov     rsi, [rax+8]
0x1800056a0  lea     rax, [rsp+528h+Context]
0x1800056a5  mov     rbp, rsi
0x1800056a8  sub     rbp, rax
0x1800056ab  lea     rax, [rsp+528h+Context]
0x1800056b0  cmp     rax, rsi
0x1800056b3  jnb     short loc_180005725
0x1800056b5  cmp     byte ptr [rbx+3260h], 0
0x1800056bc  lea     rdi, [rsp+528h+Context]
0x1800056c1  jz      loc_18000576C
0x1800056c7  mov     rdx, [rdi]
0x1800056ca  test    rdx, rdx
0x1800056cd  jz      short loc_18000571C
0x1800056cf  and     rdx, 0FFFFFFFFFFFFFFE0h
0x1800056d3  cmp     rdx, 10000h
0x1800056da  jb      short loc_18000571C
0x1800056dc  mov     rcx, [rbx+168h]
0x1800056e3  mov     rax, rdx
0x1800056e6  shr     rax, 20h
0x1800056ea  test    rcx, rcx
0x1800056ed  jz      short loc_18000571C
0x1800056ef  cmp     [rcx], eax
0x1800056f1  jnz     short loc_180005751
0x1800056f3  mov     eax, edx
0x1800056f5  shr     rax, 14h
0x1800056f9  mov     r8d, edx
0x1800056fc  mov     rcx, [rcx+rax*8+18h]
0x180005701  test    rcx, rcx
0x180005704  jz      loc_180005878
0x18000570a  shr     r8, 0Ch
0x18000570e  movzx   eax, r8b
0x180005712  mov     rcx, [rcx+rax*8+8]
0x180005717  test    rcx, rcx
0x18000571a  jnz     short loc_180005757
0x18000571c  add     rdi, 8
0x180005720  cmp     rdi, rsi
0x180005723  jb      short loc_1800056C7
0x180005725  test    byte ptr cs:Microsoft_JScriptEnableBits, 20h
0x18000572c  jnz     loc_180005845
0x180005732  mov     rax, rbp
0x180005735  mov     rcx, [rsp+528h+var_38]
0x18000573d  xor     rcx, rsp; StackCookie
0x180005740  call    __security_check_cookie
0x180005745  add     rsp, 508h
0x18000574c  pop     rdi
0x18000574d  pop     rsi
0x18000574e  pop     rbp
0x18000574f  pop     rbx
0x180005750  retn
0x180005751  mov     rcx, [rcx+8]
0x180005755  jmp     short loc_1800056EA
0x180005757  mov     rax, [rcx]
0x18000575a  mov     r8, rbx
0x18000575d  mov     rax, [rax+18h]
0x180005761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005766  jmp     short loc_18000571C
0x180005768  xor     eax, eax
0x18000576a  jmp     short loc_180005735
0x18000576c  cmp     qword ptr [rdi], 10000h
0x180005773  jb      short loc_18000577A
0x180005775  test    byte ptr [rdi], 1Fh
0x180005778  jz      short loc_180005785
0x18000577a  add     rdi, 8
0x18000577e  cmp     rdi, rsi
0x180005781  jb      short loc_18000576C
0x180005783  jmp     short loc_180005725
0x180005785  mov     rax, [rdi]
0x180005788  mov     rcx, [rbx+168h]
0x18000578f  shr     rax, 20h
0x180005793  test    rcx, rcx
0x180005796  jz      short loc_18000577A
0x180005798  cmp     [rcx], eax
0x18000579a  jnz     short loc_1800057EF
0x18000579c  mov     edx, [rdi]
0x18000579e  mov     eax, edx
0x1800057a0  shr     rax, 14h
0x1800057a4  mov     r9, [rcx+rax*8+18h]
0x1800057a9  test    r9, r9
0x1800057ac  jz      loc_180005873
0x1800057b2  shr     rdx, 0Ch
0x1800057b6  movzx   eax, dl
0x1800057b9  mov     r9, [r9+rax*8+8]
0x1800057be  test    r9, r9
0x1800057c1  jz      short loc_18000577A
0x1800057c3  movzx   r8d, byte ptr [r9+18h]
0x1800057c8  test    r8d, r8d
0x1800057cb  jz      short loc_1800057F5
0x1800057cd  sub     r8d, 1
0x1800057d1  jz      short loc_1800057F5
0x1800057d3  sub     r8d, 1
0x1800057d7  jz      short loc_180005808
0x1800057d9  cmp     r8d, 1
0x1800057dd  jnz     short loc_18000577A
0x1800057df  mov     rdx, [rdi]; void *
0x1800057e2  mov     r8, rbx; struct Recycler *
0x1800057e5  mov     rcx, r9; this
0x1800057e8  call    ?Mark@LargeHeapBlock@@QEAAXPEAXPEAVRecycler@@@Z; LargeHeapBlock::Mark(void *,Recycler *)
0x1800057ed  jmp     short loc_18000577A
0x1800057ef  mov     rcx, [rcx+8]
0x1800057f3  jmp     short loc_180005793
0x1800057f5  mov     rdx, [rdi]; void *
0x1800057f8  mov     r8, rbx; struct Recycler *
0x1800057fb  mov     rcx, r9; this
0x1800057fe  call    ?Mark@SmallNormalHeapBlock@@QEAAXPEAXPEAVRecycler@@@Z; SmallNormalHeapBlock::Mark(void *,Recycler *)
0x180005803  jmp     loc_18000577A
0x180005808  movzx   eax, word ptr [rdi]
0x18000580b  shr     eax, 5
0x18000580e  and     eax, 7Fh
0x180005811  mov     r10d, eax
0x180005814  shr     r10, 6
0x180005818  mov     edx, eax
0x18000581a  and     eax, 3Fh
0x18000581d  movzx   ecx, al
0x180005820  mov     r8, [r9+r10*8+58h]
0x180005825  bt      r8, rcx
0x180005829  jb      loc_18000577A
0x18000582f  and     edx, 3Fh
0x180005832  bts     r8, rdx
0x180005836  mov     [r9+r10*8+58h], r8
0x18000583b  inc     word ptr [r9+50h]
0x180005840  jmp     loc_18000577A
0x180005845  mov     r8, rbx
0x180005848  lea     rdx, JSCRIPT_GC_SCANSTACK_STOP
0x18000584f  call    McTemplateU0p_EventWriteTransfer
0x180005854  jmp     loc_180005732
0x180005859  mov     r8, rbx
0x18000585c  lea     rdx, JSCRIPT_GC_SCANSTACK_START
0x180005863  call    McTemplateU0p_EventWriteTransfer
0x180005868  jmp     loc_18000565D
0x18000586d  call    ?FatalInternalError@Throw@Js@@SAXXZ; Js::Throw::FatalInternalError(void)
0x180005872  int     3; Trap to Debugger
0x180005873  jmp     loc_1800057BE
0x180005878  jmp     loc_180005717
```
