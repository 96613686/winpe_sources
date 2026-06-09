# CDDMULTISURFLOCK::vDone(void)

- ea: `0x140008da4`
- end: `0x140008e89`
- name: `?vDone@CDDMULTISURFLOCK@@QEAAXXZ`
- size: `229`
- prototype: `void __fastcall(CDDMULTISURFLOCK *__hidden this)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x140002504`
- `0x140004904`
- `0x14000919c`
- `0x1400161b0`
- `0x140017518`
- `0x140019458`

## callees

- `0x140008da4`
- `0x140008e90`
- `0x140008f1c`
- `0x1400224a0`
- `0x140034204`

## import_xrefs

- `WIN32K!EngReleaseSemaphore` at `0x140008e41`
- `WIN32K!EngReleaseSemaphore` at `0x140008e41`

## string_xrefs

- `0x140008e29`: `vUnLockBmp1AndRemovePunt: cddBmp1 == NULL\n`

## pseudocode

```c
void __fastcall CDDMULTISURFLOCK::vDone(CDDMULTISURFLOCK *this)
{
  __int64 v2; // rcx
  __int64 v3; // rax
  signed __int32 v4[10]; // [rsp+0h] [rbp-28h] BYREF

  v2 = *(_QWORD *)this;
  if ( v2 || *((_QWORD *)this + 2) || *((_QWORD *)this + 4) || *((_QWORD *)this + 5) )
  {
    v3 = *((_QWORD *)this + 2);
    if ( v2 == v3 )
    {
      if ( !*((_QWORD *)this + 4) && !*((_QWORD *)this + 5) )
      {
        CDDMULTISURFLOCK::vUnLockBmp1AndRemovePunt(this);
        return;
      }
      if ( *((_BYTE *)this + 48) == 1 )
        CDDMULTISURFLOCK::vUnLockShadowR(this);
      _InterlockedOr(v4, 0);
      if ( *((_BYTE *)this + 49) == 1 )
        goto LABEL_10;
    }
    else
    {
      if ( v3 && !*((_QWORD *)this + 5) )
      {
        if ( !*((_QWORD *)this + 3) )
        {
          DbgLog("vUnLockBmp1AndRemovePunt: cddBmp1 == NULL\n");
          __debugbreak();
        }
        EngReleaseSemaphore(*(HSEMAPHORE *)(*((_QWORD *)this + 3) + 192LL));
        *((_QWORD *)this + 2) = 0;
      }
      _InterlockedOr(v4, 0);
      if ( *(_QWORD *)this && !*((_QWORD *)this + 4) )
        CDDMULTISURFLOCK::vUnLockBmp1AndRemovePunt(this);
      if ( *((_BYTE *)this + 48) )
        CDDMULTISURFLOCK::vUnLockShadowR(this);
      _InterlockedOr(v4, 0);
      if ( *((_BYTE *)this + 49) )
LABEL_10:
        CDDMULTISURFLOCK::vUnLockShadowW(this);
    }
  }
}

```

## disassembly

```asm
0x140008da4  mov     [rsp+arg_0], rbx
0x140008da9  push    rdi
0x140008daa  sub     rsp, 20h
0x140008dae  mov     rbx, rcx
0x140008db1  xor     edi, edi
0x140008db3  mov     rcx, [rcx]
0x140008db6  test    rcx, rcx
0x140008db9  jnz     short loc_140008DCD
0x140008dbb  cmp     [rbx+10h], rdi
0x140008dbf  jnz     short loc_140008DCD
0x140008dc1  cmp     [rbx+20h], rdi
0x140008dc5  jnz     short loc_140008DCD
0x140008dc7  cmp     [rbx+28h], rdi
0x140008dcb  jz      short loc_140008DFC
0x140008dcd  mov     rax, [rbx+10h]
0x140008dd1  cmp     rcx, rax
0x140008dd4  jnz     short loc_140008E18
0x140008dd6  cmp     [rbx+20h], rdi
0x140008dda  jz      short loc_140008E08
0x140008ddc  cmp     byte ptr [rbx+30h], 1
0x140008de0  jnz     short loc_140008DEA
0x140008de2  mov     rcx, rbx; this
0x140008de5  call    ?vUnLockShadowR@CDDMULTISURFLOCK@@QEAAXXZ; CDDMULTISURFLOCK::vUnLockShadowR(void)
0x140008dea  lock or [rsp+28h+var_28], edi
0x140008dee  cmp     byte ptr [rbx+31h], 1
0x140008df2  jnz     short loc_140008DFC
0x140008df4  mov     rcx, rbx; this
0x140008df7  call    ?vUnLockShadowW@CDDMULTISURFLOCK@@QEAAXXZ; CDDMULTISURFLOCK::vUnLockShadowW(void)
0x140008dfc  mov     rbx, [rsp+28h+arg_0]
0x140008e01  add     rsp, 20h
0x140008e05  pop     rdi
0x140008e06  retn
0x140008e08  cmp     [rbx+28h], rdi
0x140008e0c  jnz     short loc_140008DDC
0x140008e0e  mov     rcx, rbx; this
0x140008e11  call    ?vUnLockBmp1AndRemovePunt@CDDMULTISURFLOCK@@QEAAXXZ; CDDMULTISURFLOCK::vUnLockBmp1AndRemovePunt(void)
0x140008e16  jmp     short loc_140008DFC
0x140008e18  test    rax, rax
0x140008e1b  jz      short loc_140008E51
0x140008e1d  cmp     [rbx+28h], rdi
0x140008e21  jnz     short loc_140008E51
0x140008e23  cmp     [rbx+18h], rdi
0x140008e27  jnz     short loc_140008E36
0x140008e29  lea     rcx, aVunlockbmp1and; "vUnLockBmp1AndRemovePunt: cddBmp1 == NU"...
0x140008e30  call    ?DbgLog@@YAXPEBDZZ; DbgLog(char const *,...)
0x140008e35  int     3; Trap to Debugger
0x140008e36  mov     rcx, [rbx+18h]
0x140008e3a  mov     rcx, [rcx+0C0h]; hsem
0x140008e41  call    cs:__imp_EngReleaseSemaphore
0x140008e48  nop     dword ptr [rax+rax+00h]
0x140008e4d  mov     [rbx+10h], rdi
0x140008e51  lock or [rsp+28h+var_28], edi
0x140008e55  cmp     [rbx], rdi
0x140008e58  jz      short loc_140008E68
0x140008e5a  cmp     [rbx+20h], rdi
0x140008e5e  jnz     short loc_140008E68
0x140008e60  mov     rcx, rbx; this
0x140008e63  call    ?vUnLockBmp1AndRemovePunt@CDDMULTISURFLOCK@@QEAAXXZ; CDDMULTISURFLOCK::vUnLockBmp1AndRemovePunt(void)
0x140008e68  cmp     [rbx+30h], dil
0x140008e6c  jz      short loc_140008E76
0x140008e6e  mov     rcx, rbx; this
0x140008e71  call    ?vUnLockShadowR@CDDMULTISURFLOCK@@QEAAXXZ; CDDMULTISURFLOCK::vUnLockShadowR(void)
0x140008e76  lock or [rsp+28h+var_28], edi
0x140008e7a  cmp     [rbx+31h], dil
0x140008e7e  jz      loc_140008DFC
0x140008e84  jmp     loc_140008DF4
```
