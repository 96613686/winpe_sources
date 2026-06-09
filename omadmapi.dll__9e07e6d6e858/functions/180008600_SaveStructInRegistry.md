# SaveStructInRegistry

- ea: `0x180008600`
- end: `0x1800086ea`
- name: `SaveStructInRegistry`
- size: `234`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, int, __int64, int, unsigned __int8 *, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000d3ec`
- `0x18000db90`
- `0x18001b0d0`

## callees

- `0x180007968`
- `0x180008600`

## pseudocode

```c
__int64 __fastcall SaveStructInRegistry(
        HKEY hKey,
        int a2,
        int a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        unsigned int a7,
        unsigned __int8 *a8,
        DWORD a9)
{
  __int64 result; // rax
  unsigned int i; // edi
  __int64 v15; // rdx
  DWORD dwType; // r9d
  __int64 v17; // rax
  unsigned __int8 *v18; // r8
  __int64 v19; // rcx

  result = 0;
  for ( i = 0; i < a5; ++i )
  {
    v15 = 32LL * i;
    if ( !a2 || (a3 & *(_DWORD *)(v15 + a4 + 8)) != 0 )
    {
      dwType = *(_DWORD *)(v15 + a4 + 16);
      v17 = *(unsigned int *)(v15 + a4 + 20);
      if ( dwType == 4 )
      {
        v18 = (unsigned __int8 *)(a6 + v17);
      }
      else
      {
        if ( (unsigned int)v17 > a7 )
          return 2147500037LL;
        v18 = *(unsigned __int8 **)(v17 + a6);
      }
      v19 = *(unsigned int *)(v15 + a4 + 24);
      if ( (_DWORD)v19 == -1 )
      {
        LODWORD(v19) = -1;
      }
      else if ( (int)v19 < 0 )
      {
        LODWORD(v19) = v19 & 0x7FFFFFFF;
        if ( (unsigned int)v19 > a7 )
          return 2147500037LL;
        LODWORD(v19) = *(_DWORD *)(v19 + a6);
      }
      result = SetRegValue(hKey, *(LPCWSTR *)(v15 + a4), *(_DWORD *)(v15 + a4 + 12), a8, a9, dwType, v18, v19);
      if ( (int)result < 0 )
        return result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180008600  push    rbx
0x180008602  push    rsi
0x180008603  push    rdi
0x180008604  push    r12
0x180008606  push    r13
0x180008608  push    r14
0x18000860a  push    r15
0x18000860c  sub     rsp, 40h
0x180008610  xor     eax, eax
0x180008612  xor     edi, edi
0x180008614  mov     rbx, r9
0x180008617  mov     r14d, r8d
0x18000861a  mov     r15d, edx
0x18000861d  mov     r13, rcx
0x180008620  cmp     [rsp+78h+arg_20], eax
0x180008627  jbe     loc_1800086D9
0x18000862d  mov     r12d, [rsp+78h+arg_40]
0x180008635  mov     rsi, [rsp+78h+arg_28]
0x18000863d  mov     edx, edi
0x18000863f  shl     rdx, 5
0x180008643  test    r15d, r15d
0x180008646  jz      short loc_18000864F
0x180008648  test    [rdx+rbx+8], r14d
0x18000864d  jz      short loc_1800086C3
0x18000864f  mov     r9d, [rdx+rbx+10h]
0x180008654  mov     eax, [rdx+rbx+14h]
0x180008658  cmp     r9d, 4
0x18000865c  jnz     short loc_180008664
0x18000865e  lea     r8, [rsi+rax]
0x180008662  jmp     short loc_180008671
0x180008664  cmp     eax, [rsp+78h+arg_30]
0x18000866b  ja      short loc_1800086D4
0x18000866d  mov     r8, [rax+rsi]
0x180008671  mov     ecx, [rdx+rbx+18h]
0x180008675  cmp     ecx, 0FFFFFFFFh
0x180008678  jz      short loc_180008690
0x18000867a  test    ecx, ecx
0x18000867c  jns     short loc_180008693
0x18000867e  btr     ecx, 1Fh
0x180008682  cmp     ecx, [rsp+78h+arg_30]
0x180008689  ja      short loc_1800086D4
0x18000868b  mov     ecx, [rcx+rsi]
0x18000868e  jmp     short loc_180008693
0x180008690  or      ecx, 0FFFFFFFFh
0x180008693  mov     [rsp+78h+var_40], ecx; unsigned int
0x180008697  mov     rcx, r13; hKey
0x18000869a  mov     [rsp+78h+var_48], r8; unsigned __int8 *
0x18000869f  mov     r8d, [rdx+rbx+0Ch]; int
0x1800086a4  mov     rdx, [rdx+rbx]; lpValueName
0x1800086a8  mov     [rsp+78h+dwType], r9d; dwType
0x1800086ad  mov     r9, [rsp+78h+arg_38]; unsigned __int8 *
0x1800086b5  mov     [rsp+78h+var_58], r12d; unsigned int
0x1800086ba  call    ?SetRegValue@@YAJPEAUHKEY__@@PEBGHPEAEKK2K@Z; SetRegValue(HKEY__ *,ushort const *,int,uchar *,ulong,ulong,uchar *,ulong)
0x1800086bf  test    eax, eax
0x1800086c1  js      short loc_1800086D9
0x1800086c3  inc     edi
0x1800086c5  cmp     edi, [rsp+78h+arg_20]
0x1800086cc  jb      loc_18000863D
0x1800086d2  jmp     short loc_1800086D9
0x1800086d4  mov     eax, 80004005h
0x1800086d9  add     rsp, 40h
0x1800086dd  pop     r15
0x1800086df  pop     r14
0x1800086e1  pop     r13
0x1800086e3  pop     r12
0x1800086e5  pop     rdi
0x1800086e6  pop     rsi
0x1800086e7  pop     rbx
0x1800086e8  retn
```
