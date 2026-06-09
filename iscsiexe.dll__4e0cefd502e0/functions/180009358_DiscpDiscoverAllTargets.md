# DiscpDiscoverAllTargets

- ea: `0x180009358`
- end: `0x180009400`
- name: `DiscpDiscoverAllTargets`
- size: `168`
- prototype: `__int64 __fastcall(char)`
- caller_count: `10`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180003840`
- `0x180003a70`
- `0x180003bc0`
- `0x180003da0`
- `0x180004170`
- `0x180004850`
- `0x180004980`
- `0x180007c44`
- `0x180009898`
- `0x180012b70`

## callees

- `0x180002788`
- `0x1800027cc`
- `0x1800078ac`
- `0x180007bb4`
- `0x180009358`
- `0x180009408`
- `0x180009618`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800093ed`
- `ntdll!RtlLeaveCriticalSection` at `0x1800093ed`
- `ntdll!RtlEnterCriticalSection` at `0x18000936b`
- `ntdll!RtlEnterCriticalSection` at `0x18000936b`

## pseudocode

```c
__int64 __fastcall DiscpDiscoverAllTargets(char a1)
{
  _UNKNOWN **v2; // rbx
  _UNKNOWN **v3; // rcx
  __int128 v5; // [rsp+20h] [rbp-18h] BYREF

  RtlEnterCriticalSection(&DiscpDiscoveryCritSection);
  if ( !DiscpTargetsDiscovered || a1 )
  {
    DiscpTargetsDiscovered = 0;
    DiscpRemoveTargetsByTag(1);
    DiscpDiscoverViaStaticTargets();
    DiscpDiscoverViaAllSNS();
    DiscpDiscoverViaStaticSendTargets();
    v2 = (_UNKNOWN **)DiscpInitiatorInstanceList;
    v5 = 0;
    while ( v2 != &DiscpInitiatorInstanceList )
    {
      v3 = v2;
      v2 = (_UNKNOWN **)*v2;
      if ( (*((_BYTE *)v3 + 20) & 2) == 0 && !(unsigned int)DiscpDiscoverViaHBA(v3, &v5) )
        DiscpInsertTargetList(&v5);
    }
    DiscpTargetsDiscovered = 1;
  }
  RtlLeaveCriticalSection(&DiscpDiscoveryCritSection);
  return 0;
}

```

## disassembly

```asm
0x180009358  mov     [rsp+arg_0], rbx
0x18000935d  push    rdi
0x18000935e  sub     rsp, 30h
0x180009362  mov     bl, cl
0x180009364  lea     rcx, DiscpDiscoveryCritSection; CriticalSection
0x18000936b  call    cs:__imp_RtlEnterCriticalSection
0x180009371  cmp     cs:DiscpTargetsDiscovered, 0
0x180009378  jz      short loc_18000937E
0x18000937a  test    bl, bl
0x18000937c  jz      short loc_1800093E6
0x18000937e  mov     ecx, 1
0x180009383  mov     cs:DiscpTargetsDiscovered, 0
0x18000938a  call    DiscpRemoveTargetsByTag
0x18000938f  call    DiscpDiscoverViaStaticTargets
0x180009394  call    DiscpDiscoverViaAllSNS
0x180009399  call    DiscpDiscoverViaStaticSendTargets
0x18000939e  mov     rbx, cs:DiscpInitiatorInstanceList
0x1800093a5  lea     rdi, DiscpInitiatorInstanceList
0x1800093ac  xorps   xmm0, xmm0
0x1800093af  movups  [rsp+38h+var_18], xmm0
0x1800093b4  jmp     short loc_1800093DA
0x1800093b6  mov     rcx, rbx
0x1800093b9  mov     rbx, [rbx]
0x1800093bc  test    byte ptr [rcx+14h], 2
0x1800093c0  jnz     short loc_1800093DA
0x1800093c2  lea     rdx, [rsp+38h+var_18]
0x1800093c7  call    DiscpDiscoverViaHBA
0x1800093cc  test    eax, eax
0x1800093ce  jnz     short loc_1800093DA
0x1800093d0  lea     rcx, [rsp+38h+var_18]
0x1800093d5  call    DiscpInsertTargetList
0x1800093da  cmp     rbx, rdi
0x1800093dd  jnz     short loc_1800093B6
0x1800093df  mov     cs:DiscpTargetsDiscovered, 1
0x1800093e6  lea     rcx, DiscpDiscoveryCritSection; CriticalSection
0x1800093ed  call    cs:__imp_RtlLeaveCriticalSection
0x1800093f3  mov     rbx, [rsp+38h+arg_0]
0x1800093f8  xor     eax, eax
0x1800093fa  add     rsp, 30h
0x1800093fe  pop     rdi
0x1800093ff  retn
```
