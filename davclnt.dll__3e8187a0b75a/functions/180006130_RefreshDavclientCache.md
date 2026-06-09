# RefreshDavclientCache

- ea: `0x180006130`
- end: `0x180006289`
- name: `RefreshDavclientCache`
- size: `345`
- prototype: `void __fastcall(STRSAFE_LPCWSTR pszSrc, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800051e0`

## callees

- `0x180006130`
- `0x180009c00`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800061d1`
- `msvcrt!_wcsicmp` at `0x1800061d1`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000615f`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000615f`
- `ntdll!RtlReleaseResource` at `0x180006282`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000614d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000614d`

## pseudocode

```c
void __fastcall RefreshDavclientCache(STRSAFE_LPCWSTR pszSrc, int a2)
{
  unsigned int v4; // edi
  unsigned int v5; // ebp
  ULONGLONG TickCount64; // r14
  unsigned int i; // esi
  __int64 v8; // r12
  __int64 *v9; // r15
  __int64 v10; // rdx
  __int64 v11; // r10
  __int64 v12; // r10
  __int64 v13; // r11

  v4 = 10;
  v5 = 0;
  TickCount64 = GetTickCount64();
  RtlAcquireResourceExclusive(&DavclientCacheLock, 1u);
  for ( i = 0; i != 10; ++i )
  {
    v8 = 67LL * i;
    if ( BYTE4(DavclientCache[v8 + 66]) )
    {
      v9 = &DavclientCache[v8];
      if ( TickCount64 <= 0x493E0 || TickCount64 - 300000 <= *v9 )
      {
        if ( !_wcsicmp((const wchar_t *)&DavclientCache[v8 + 1], pszSrc) && LODWORD(DavclientCache[v8 + 66]) == a2 )
          goto LABEL_22;
        if ( v4 == 10 && DavclientCache[67 * v5] > (unsigned __int64)*v9 )
          v5 = i;
      }
      else
      {
        BYTE4(DavclientCache[v8 + 66]) = 0;
        if ( i < v4 )
          v4 = i;
      }
    }
    else if ( i < v4 )
    {
      v4 = i;
    }
  }
  v10 = -1;
  if ( v4 >= 0xA )
    v4 = v5;
  v11 = 67LL * v4;
  BYTE4(DavclientCache[v11 + 66]) = 0;
  DavclientCache[v11] = TickCount64;
  do
    ++v10;
  while ( pszSrc[v10] );
  if ( StringCchCopyW((STRSAFE_LPWSTR)&DavclientCache[v11 + 1], v10 + 1, pszSrc) >= 0 )
  {
    *(_DWORD *)(v12 + v13 + 528) = a2;
    *(_BYTE *)(v12 + v13 + 532) = 1;
  }
LABEL_22:
  RtlReleaseResource(&DavclientCacheLock);
}

```

## disassembly

```asm
0x180006130  mov     [rsp+arg_10], rbx
0x180006135  push    rbp
0x180006136  push    rsi
0x180006137  push    rdi
0x180006138  push    r13
0x18000613a  push    r14
0x18000613c  sub     rsp, 20h
0x180006140  mov     r13d, edx
0x180006143  mov     rbx, rcx
0x180006146  mov     edi, 0Ah
0x18000614b  xor     ebp, ebp
0x18000614d  call    cs:__imp_GetTickCount64
0x180006153  mov     dl, 1; Wait
0x180006155  lea     rcx, DavclientCacheLock; Resource
0x18000615c  mov     r14, rax
0x18000615f  call    cs:__imp_RtlAcquireResourceExclusive
0x180006165  mov     [rsp+48h+arg_0], r12
0x18000616a  lea     r11, DavclientCache
0x180006171  xor     esi, esi
0x180006173  mov     [rsp+48h+arg_8], r15
0x180006178  cmp     esi, 0Ah
0x18000617b  jz      loc_18000620B
0x180006181  mov     ecx, esi
0x180006183  imul    r12, rcx, 218h
0x18000618a  lea     rcx, [r12+r11]
0x18000618e  cmp     byte ptr [rcx+214h], 0
0x180006195  jnz     short loc_18000619F
0x180006197  cmp     esi, edi
0x180006199  jnb     short loc_180006204
0x18000619b  mov     edi, esi
0x18000619d  jmp     short loc_180006204
0x18000619f  lea     r15, [r12+r11]
0x1800061a3  cmp     r14, 493E0h
0x1800061aa  jbe     short loc_1800061C7
0x1800061ac  lea     rax, [r14-493E0h]
0x1800061b3  cmp     rax, [r15]
0x1800061b6  jbe     short loc_1800061C7
0x1800061b8  mov     byte ptr [rcx+214h], 0
0x1800061bf  cmp     esi, edi
0x1800061c1  jnb     short loc_180006204
0x1800061c3  mov     edi, esi
0x1800061c5  jmp     short loc_180006204
0x1800061c7  lea     rcx, [r11+8]
0x1800061cb  mov     rdx, rbx; String2
0x1800061ce  add     rcx, r12; String1
0x1800061d1  call    cs:__imp__wcsicmp
0x1800061d7  lea     r11, DavclientCache
0x1800061de  test    eax, eax
0x1800061e0  jnz     short loc_1800061EC
0x1800061e2  cmp     [r12+r11+210h], r13d
0x1800061ea  jz      short loc_180006261
0x1800061ec  cmp     edi, 0Ah
0x1800061ef  jnz     short loc_180006204
0x1800061f1  mov     eax, ebp
0x1800061f3  imul    rcx, rax, 218h
0x1800061fa  mov     rax, [r15]
0x1800061fd  cmp     [rcx+r11], rax
0x180006201  cmova   ebp, esi
0x180006204  inc     esi
0x180006206  jmp     loc_180006178
0x18000620b  cmp     edi, 0Ah
0x18000620e  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180006215  cmovnb  edi, ebp
0x180006218  mov     eax, edi
0x18000621a  imul    r10, rax, 218h
0x180006221  mov     byte ptr [r10+r11+214h], 0
0x18000622a  mov     [r10+r11], r14
0x18000622e  xchg    ax, ax
0x180006230  inc     rdx
0x180006233  cmp     word ptr [rbx+rdx*2], 0
0x180006238  jnz     short loc_180006230
0x18000623a  lea     rcx, [r11+8]
0x18000623e  inc     rdx; cchDest
0x180006241  add     rcx, r10; pszDest
0x180006244  mov     r8, rbx; pszSrc
0x180006247  call    StringCchCopyW
0x18000624c  test    eax, eax
0x18000624e  js      short loc_180006261
0x180006250  mov     [r10+r11+210h], r13d
0x180006258  mov     byte ptr [r10+r11+214h], 1
0x180006261  lea     rcx, DavclientCacheLock
0x180006268  mov     r15, [rsp+48h+arg_8]
0x18000626d  mov     r12, [rsp+48h+arg_0]
0x180006272  mov     rbx, [rsp+48h+arg_10]
0x180006277  add     rsp, 20h
0x18000627b  pop     r14
0x18000627d  pop     r13
0x18000627f  pop     rdi
0x180006280  pop     rsi
0x180006281  pop     rbp
0x180006282  jmp     cs:__imp_RtlReleaseResource
```
