# NTCache::getMode(ushort const *)

- ea: `0x18001df3c`
- end: `0x18001dfd7`
- name: `?getMode@NTCache@@QEAA?AW4Mode@NTDomain@@PEBG@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180024630`

## callees

- `0x18001dddc`
- `0x18001df3c`
- `0x18001f5d0`
- `0x18001f7b4`
- `0x18001fa44`
- `0x18001fb4c`
- `0x18001fe10`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001dfbc`
- `KERNEL32!LeaveCriticalSection` at `0x18001dfbc`
- `KERNEL32!EnterCriticalSection` at `0x18001df83`
- `KERNEL32!EnterCriticalSection` at `0x18001df83`
- `KERNEL32!TryEnterCriticalSection` at `0x18001df67`
- `KERNEL32!TryEnterCriticalSection` at `0x18001df67`
- `KERNEL32!SwitchToThread` at `0x18001df78`
- `KERNEL32!SwitchToThread` at `0x18001df78`

## pseudocode

```c
__int64 __fastcall NTCache::getMode(NTCache *a1, const unsigned __int16 *a2)
{
  unsigned int SpinCount; // edi
  LPCRITICAL_SECTION v3; // rbx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+30h] [rbp+8h] BYREF

  SpinCount = 0;
  lpCriticalSection = 0;
  if ( !(unsigned int)NTCache::getDomain(a1, a2, (struct NTDomain **)&lpCriticalSection) )
  {
    v3 = lpCriticalSection;
    while ( !TryEnterCriticalSection(v3) )
    {
      if ( (int)++SpinCount >= 100 )
      {
        EnterCriticalSection(v3);
        break;
      }
      SwitchToThread();
    }
    if ( (unsigned int)NTDomain::isExpired((NTDomain *)v3) )
    {
      if ( (unsigned int)NTDomain::isConnected((NTDomain *)v3) )
        v3[3].LockCount = NTDomain::readDomainMode((NTDomain *)v3);
      else
        NTDomain::findServer((NTDomain *)v3);
    }
    SpinCount = v3[2].SpinCount;
    LeaveCriticalSection(v3);
    NTDomain::Release((NTDomain *)v3);
  }
  return SpinCount;
}

```

## disassembly

```asm
0x18001df3c  mov     rax, rsp
0x18001df3f  mov     [rax+10h], rbx
0x18001df43  mov     [rax+8], rcx
0x18001df47  push    rdi
0x18001df48  sub     rsp, 20h
0x18001df4c  xor     edi, edi
0x18001df4e  lea     r8, [rax+8]; struct NTDomain **
0x18001df52  mov     [rax+8], rdi
0x18001df56  call    ?getDomain@NTCache@@QEAAKPEBGPEAPEAVNTDomain@@@Z; NTCache::getDomain(ushort const *,NTDomain * *)
0x18001df5b  test    eax, eax
0x18001df5d  jnz     short loc_18001DFCA
0x18001df5f  mov     rbx, [rsp+28h+lpCriticalSection]
0x18001df64  mov     rcx, rbx; lpCriticalSection
0x18001df67  call    cs:__imp_TryEnterCriticalSection
0x18001df6d  test    eax, eax
0x18001df6f  jnz     short loc_18001DF89
0x18001df71  inc     edi
0x18001df73  cmp     edi, 64h ; 'd'
0x18001df76  jge     short loc_18001DF80
0x18001df78  call    cs:__imp_SwitchToThread
0x18001df7e  jmp     short loc_18001DF64
0x18001df80  mov     rcx, rbx; lpCriticalSection
0x18001df83  call    cs:__imp_EnterCriticalSection
0x18001df89  mov     rcx, rbx; this
0x18001df8c  call    ?isExpired@NTDomain@@IEAAHXZ; NTDomain::isExpired(void)
0x18001df91  test    eax, eax
0x18001df93  jz      short loc_18001DFB6
0x18001df95  mov     rcx, rbx; this
0x18001df98  call    ?isConnected@NTDomain@@IEAAHXZ; NTDomain::isConnected(void)
0x18001df9d  mov     rcx, rbx; this
0x18001dfa0  test    eax, eax
0x18001dfa2  jz      short loc_18001DFB1
0x18001dfa4  call    ?readDomainMode@NTDomain@@IEAAKXZ; NTDomain::readDomainMode(void)
0x18001dfa9  mov     [rbx+80h], eax
0x18001dfaf  jmp     short loc_18001DFB6
0x18001dfb1  call    ?findServer@NTDomain@@IEAAXXZ; NTDomain::findServer(void)
0x18001dfb6  mov     edi, [rbx+70h]
0x18001dfb9  mov     rcx, rbx; lpCriticalSection
0x18001dfbc  call    cs:__imp_LeaveCriticalSection
0x18001dfc2  mov     rcx, rbx; this
0x18001dfc5  call    ?Release@NTDomain@@QEAAXXZ; NTDomain::Release(void)
0x18001dfca  mov     rbx, [rsp+28h+arg_8]
0x18001dfcf  mov     eax, edi
0x18001dfd1  add     rsp, 20h
0x18001dfd5  pop     rdi
0x18001dfd6  retn
```
