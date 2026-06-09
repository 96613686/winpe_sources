# RegUtils::GetVolatileRegistryLocation(MapsRegKeys,ushort *,ulong)

- ea: `0x18000c368`
- end: `0x18000c3ec`
- name: `?GetVolatileRegistryLocation@RegUtils@@CAJW4MapsRegKeys@@PEAGK@Z`
- size: `132`
- prototype: `int __fastcall(__int64, _WORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000af38`

## callees

- `0x18000c368`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000c3e1`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000c3e1`

## string_xrefs

- `0x18000c3d7`: `RegUtils::GetVolatileRegistryLocation`

## pseudocode

```c
int __fastcall RegUtils::GetVolatileRegistryLocation(__int64 a1, _WORD *a2)
{
  __int64 v2; // rax
  const wchar_t *v3; // rcx
  __int64 v4; // r8
  _WORD *v5; // rcx

  v2 = 2147483646;
  v3 = L"System\\Maps\\Storage\\Volatile";
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
0x18000c368  sub     rsp, 28h
0x18000c36c  mov     eax, 7FFFFFFEh
0x18000c371  lea     rcx, aSystemMapsStor; "System\\Maps\\Storage\\Volatile"
0x18000c378  mov     r8d, 104h
0x18000c37e  xor     r10d, r10d
0x18000c381  test    rax, rax
0x18000c384  jz      short loc_18000C3A5
0x18000c386  movzx   r9d, word ptr [rcx]
0x18000c38a  test    r9w, r9w
0x18000c38e  jz      short loc_18000C3A5
0x18000c390  mov     [rdx], r9w
0x18000c394  add     rcx, 2
0x18000c398  add     rdx, 2
0x18000c39c  dec     rax
0x18000c39f  sub     r8, 1
0x18000c3a3  jnz     short loc_18000C381
0x18000c3a5  mov     rax, r8
0x18000c3a8  lea     rcx, [rdx-2]
0x18000c3ac  neg     rax
0x18000c3af  sbb     r9d, r9d
0x18000c3b2  not     r9d
0x18000c3b5  and     r9d, 8007007Ah
0x18000c3bc  test    r8, r8
0x18000c3bf  cmovnz  rcx, rdx
0x18000c3c3  mov     [rcx], r10w
0x18000c3c7  jz      short loc_18000C3D1
0x18000c3c9  mov     eax, r10d
0x18000c3cc  add     rsp, 28h
0x18000c3d0  retn
0x18000c3d1  mov     r8d, 43Ah
0x18000c3d7  lea     rdx, aRegutilsGetvol; "RegUtils::GetVolatileRegistryLocation"
0x18000c3de  mov     ecx, r9d
0x18000c3e1  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000c3e7  add     rsp, 28h
0x18000c3eb  retn
```
