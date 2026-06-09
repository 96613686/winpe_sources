# RegUtils::GetVolatileRegistryLocation(MapsRegKeys,ushort *,ulong)

- ea: `0x180007ca0`
- end: `0x180007d24`
- name: `?GetVolatileRegistryLocation@RegUtils@@CAJW4MapsRegKeys@@PEAGK@Z`
- size: `132`
- prototype: `int __fastcall(__int64, _WORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800072f0`

## callees

- `0x180007ca0`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180007d19`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180007d19`

## string_xrefs

- `0x180007d0f`: `RegUtils::GetVolatileRegistryLocation`

## pseudocode

```c
int __fastcall RegUtils::GetVolatileRegistryLocation(__int64 a1, _WORD *a2)
{
  __int64 v2; // rax
  const wchar_t *v3; // rcx
  __int64 v4; // r8
  _WORD *v5; // rcx

  v2 = 2147483646;
  v3 = L"System\\Maps\\Volatile";
  v4 = 260;
  do
  {
    if ( !v2 )
      break;
    if ( !*v3 )
      break;
    *a2++ = *v3++;
    --v2;
    --v4;
  }
  while ( v4 );
  v5 = a2 - 1;
  if ( v4 )
    v5 = a2;
  *v5 = 0;
  if ( v4 )
    return 0;
  else
    return ZTraceReportPropagationNoThis(-2147024774, "RegUtils::GetVolatileRegistryLocation", 1082);
}

```

## disassembly

```asm
0x180007ca0  sub     rsp, 28h
0x180007ca4  mov     eax, 7FFFFFFEh
0x180007ca9  lea     rcx, aSystemMapsVola; "System\\Maps\\Volatile"
0x180007cb0  mov     r8d, 104h
0x180007cb6  xor     r10d, r10d
0x180007cb9  test    rax, rax
0x180007cbc  jz      short loc_180007CDD
0x180007cbe  movzx   r9d, word ptr [rcx]
0x180007cc2  test    r9w, r9w
0x180007cc6  jz      short loc_180007CDD
0x180007cc8  mov     [rdx], r9w
0x180007ccc  add     rcx, 2
0x180007cd0  add     rdx, 2
0x180007cd4  dec     rax
0x180007cd7  sub     r8, 1
0x180007cdb  jnz     short loc_180007CB9
0x180007cdd  mov     rax, r8
0x180007ce0  lea     rcx, [rdx-2]
0x180007ce4  neg     rax
0x180007ce7  sbb     r9d, r9d
0x180007cea  not     r9d
0x180007ced  and     r9d, 8007007Ah
0x180007cf4  test    r8, r8
0x180007cf7  cmovnz  rcx, rdx
0x180007cfb  mov     [rcx], r10w
0x180007cff  jz      short loc_180007D09
0x180007d01  mov     eax, r10d
0x180007d04  add     rsp, 28h
0x180007d08  retn
0x180007d09  mov     r8d, 43Ah
0x180007d0f  lea     rdx, aRegutilsGetvol; "RegUtils::GetVolatileRegistryLocation"
0x180007d16  mov     ecx, r9d
0x180007d19  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180007d1f  add     rsp, 28h
0x180007d23  retn
```
