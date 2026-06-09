# DockCache::DevnodeCreated(ushort const *,IAepDevnode *,long)

- ea: `0x180011994`
- end: `0x180011ac6`
- name: `?DevnodeCreated@DockCache@@QEAAXPEBGPEAUIAepDevnode@@J@Z`
- size: `306`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, const unsigned __int16 *, struct IAepDevnode *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000e7d0`

## callees

- `0x1800118e0`
- `0x180011994`
- `0x180011c2c`
- `0x180013788`
- `0x18001ca4a`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800119b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011a39`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800119b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011a39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011aa1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011aa1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011abf`

## pseudocode

```c
void __fastcall DockCache::DevnodeCreated(
        struct _RTL_CRITICAL_SECTION *this,
        const unsigned __int16 *a2,
        struct IAepDevnode *a3,
        int a4)
{
  int v8; // r8d
  wchar_t *v9; // rsi
  ULONG_PTR SpinCount; // rbx
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // rcx
  wchar_t *String2; // [rsp+70h] [rbp+8h] BYREF

  EnterCriticalSection(this);
  String2 = 0;
  if ( DockCache::FindDock((DockCache *)this, a2, (struct Dock **)&String2) >= 0 )
  {
    v9 = String2;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qqSq(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, v8, (_DWORD)this, (char)String2, (__int64)a2, (char)a3);
    }
    Dock::DevnodeCreated((struct IAepDevnode **)v9, a3, a4);
    String2 = (wchar_t *)this;
    EnterCriticalSection(this);
    SpinCount = this[1].SpinCount;
    while ( 1 )
    {
      SpinCount = *(_QWORD *)SpinCount;
      if ( SpinCount == this[1].SpinCount )
        break;
      if ( !wcsncmp_0((const wchar_t *)(SpinCount + 16), v9, 0x125u) )
      {
        v11 = *((unsigned int *)v9 + 729);
        if ( *((_BYTE *)v9 + 2913) )
        {
          v12 = 3;
          if ( (int)v11 < 0 )
            v12 = 0;
        }
        else
        {
          v12 = 1;
        }
        v13 = *(_QWORD *)(SpinCount + 608);
        if ( v13 )
          (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v13 + 64LL))(v13, v12, v11);
      }
    }
    LeaveCriticalSection(this);
  }
  LeaveCriticalSection(this);
}

```

## disassembly

```asm
0x180011994  mov     [rsp+arg_8], rbx
0x180011999  mov     [rsp+arg_10], rbp
0x18001199e  push    rsi
0x18001199f  push    rdi
0x1800119a0  push    r14
0x1800119a2  sub     rsp, 50h
0x1800119a6  mov     r14d, r9d
0x1800119a9  mov     rbp, r8
0x1800119ac  mov     rbx, rdx
0x1800119af  mov     rdi, rcx
0x1800119b2  mov     [rsp+68h+var_28], rcx
0x1800119b7  call    cs:__imp_EnterCriticalSection
0x1800119bd  nop
0x1800119be  mov     [rsp+68h+String2], 0
0x1800119c7  lea     r8, [rsp+68h+String2]; struct Dock **
0x1800119cc  mov     rdx, rbx; unsigned __int16 *
0x1800119cf  mov     rcx, rdi; this
0x1800119d2  call    ?FindDock@DockCache@@AEAAJPEBGPEAPEAVDock@@@Z; DockCache::FindDock(ushort const *,Dock * *)
0x1800119d7  test    eax, eax
0x1800119d9  js      loc_180011AA8
0x1800119df  lea     rax, WPP_GLOBAL_Control
0x1800119e6  mov     rsi, [rsp+68h+String2]
0x1800119eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800119f2  cmp     rcx, rax
0x1800119f5  jz      short loc_180011A23
0x1800119f7  cmp     byte ptr [rcx+19h], 3
0x1800119fb  jb      short loc_180011A23
0x1800119fd  test    byte ptr [rcx+1Ch], 1
0x180011a01  jz      short loc_180011A23
0x180011a03  mov     edx, 40h ; '@'
0x180011a08  mov     [rsp+68h+var_38], rbp
0x180011a0d  mov     [rsp+68h+var_40], rbx
0x180011a12  mov     [rsp+68h+var_48], rsi
0x180011a17  mov     r9, rdi
0x180011a1a  mov     rcx, [rcx+10h]
0x180011a1e  call    WPP_SF_qqSq
0x180011a23  mov     r8d, r14d; int
0x180011a26  mov     rdx, rbp; struct IAepDevnode *
0x180011a29  mov     rcx, rsi; this
0x180011a2c  call    ?DevnodeCreated@Dock@@QEAAXPEAUIAepDevnode@@J@Z; Dock::DevnodeCreated(IAepDevnode *,long)
0x180011a31  mov     [rsp+68h+String2], rdi
0x180011a36  mov     rcx, rdi; lpCriticalSection
0x180011a39  call    cs:__imp_EnterCriticalSection
0x180011a3f  nop
0x180011a40  mov     rbx, [rdi+48h]
0x180011a44  mov     rbx, [rbx]
0x180011a47  cmp     rbx, [rdi+48h]
0x180011a4b  jz      short loc_180011A9E
0x180011a4d  lea     rcx, [rbx+10h]; String1
0x180011a51  mov     r8d, 125h; MaxCount
0x180011a57  mov     rdx, rsi; String2
0x180011a5a  call    wcsncmp_0
0x180011a5f  test    eax, eax
0x180011a61  jnz     short loc_180011A44
0x180011a63  mov     r8d, [rsi+0B64h]
0x180011a6a  cmp     [rsi+0B61h], al
0x180011a70  jnz     short loc_180011A77
0x180011a72  lea     edx, [rax+1]
0x180011a75  jmp     short loc_180011A84
0x180011a77  mov     edx, 3
0x180011a7c  xor     eax, eax
0x180011a7e  test    r8d, r8d
0x180011a81  cmovs   edx, eax
0x180011a84  mov     rcx, [rbx+260h]
0x180011a8b  test    rcx, rcx
0x180011a8e  jz      short loc_180011A44
0x180011a90  mov     rax, [rcx]
0x180011a93  mov     rax, [rax+40h]
0x180011a97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a9c  jmp     short loc_180011A44
0x180011a9e  mov     rcx, rdi; lpCriticalSection
0x180011aa1  call    cs:__imp_LeaveCriticalSection
0x180011aa7  nop
0x180011aa8  mov     rcx, rdi
0x180011aab  lea     r11, [rsp+68h+var_18]
0x180011ab0  mov     rbx, [r11+28h]
0x180011ab4  mov     rbp, [r11+30h]
0x180011ab8  mov     rsp, r11
0x180011abb  pop     r14
0x180011abd  pop     rdi
0x180011abe  pop     rsi
0x180011abf  jmp     cs:__imp_LeaveCriticalSection
```
