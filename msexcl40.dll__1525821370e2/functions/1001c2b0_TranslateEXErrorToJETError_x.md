# TranslateEXErrorToJETError(x)

- ea: `0x1001c2b0`
- end: `0x1001c32b`
- name: `_TranslateEXErrorToJETError@4`
- size: `123`
- prototype: `int __thiscall(_DWORD)`
- caller_count: `20`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x10006bd0`
- `0x1001abf0`
- `0x1001b1e0`
- `0x1001b2f0`
- `0x1001b4b0`
- `0x1001b5e0`
- `0x1001b770`
- `0x1001bb70`
- `0x1001bbd0`
- `0x1001bc20`
- `0x1001bc80`
- `0x1001c090`
- `0x1001d7d0`
- `0x1001d820`
- `0x1001d870`
- `0x1001e5c0`
- `0x10029730`
- `0x10029b60`
- `0x1002c79f`
- `0x1002db68`

## callees

- `0x1001c2b0`
- `0x10035b40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1001c2d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1001c2d6`

## pseudocode

```c
int __thiscall TranslateEXErrorToJETError(void *this)
{
  int v1; // edi
  int result; // eax
  DWORD CurrentProcessId; // eax
  _DWORD *v4; // ecx

  v1 = abs32((int)this);
  if ( v1 > 32 || (result = dword_10004DB0[v1], result == -5016) )
  {
    if ( dword_1003AE5C )
    {
      CurrentProcessId = GetCurrentProcessId();
      v4 = (_DWORD *)dword_1003AE68;
      if ( dword_1003AE68 )
      {
        while ( v4[4] != CurrentProcessId )
        {
          v4 = (_DWORD *)*v4;
          if ( !v4 )
            goto LABEL_7;
        }
      }
      else
      {
LABEL_7:
        v4 = 0;
      }
      (*(void (__thiscall **)(_DWORD, int, int *, int *, int *, int, int, _DWORD, _DWORD))(v4[7] + 44))(
        *(_DWORD *)(v4[7] + 44),
        dword_1003AE5C,
        &dword_100015E4,
        &dword_100015E4,
        &dword_100015E4,
        -8171,
        v1,
        0,
        0);
    }
    return -5016;
  }
  return result;
}

```

## disassembly

```asm
0x1001c2b0  mov     eax, ecx
0x1001c2b2  push    edi
0x1001c2b3  cdq
0x1001c2b4  mov     edi, eax
0x1001c2b6  xor     edi, edx
0x1001c2b8  sub     edi, edx
0x1001c2ba  cmp     edi, 20h ; ' '
0x1001c2bd  jg      short loc_1001C2CD
0x1001c2bf  mov     eax, ds:dword_10004DB0[edi*4]
0x1001c2c6  cmp     eax, 0FFFFEC68h
0x1001c2cb  jnz     short loc_1001C329
0x1001c2cd  cmp     dword_1003AE5C, 0
0x1001c2d4  jz      short loc_1001C324
0x1001c2d6  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x1001c2dc  mov     ecx, dword_1003AE68
0x1001c2e2  test    ecx, ecx
0x1001c2e4  jz      short loc_1001C2F1
0x1001c2e6  cmp     [ecx+10h], eax
0x1001c2e9  jz      short loc_1001C2F3
0x1001c2eb  mov     ecx, [ecx]
0x1001c2ed  test    ecx, ecx
0x1001c2ef  jnz     short loc_1001C2E6
0x1001c2f1  xor     ecx, ecx
0x1001c2f3  push    esi
0x1001c2f4  mov     esi, [ecx+1Ch]
0x1001c2f7  push    0
0x1001c2f9  push    0
0x1001c2fb  push    edi
0x1001c2fc  mov     esi, [esi+2Ch]
0x1001c2ff  mov     ecx, esi
0x1001c301  push    0FFFFE015h
0x1001c306  push    offset dword_100015E4
0x1001c30b  push    offset dword_100015E4
0x1001c310  push    offset dword_100015E4
0x1001c315  push    dword_1003AE5C
0x1001c31b  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001c321  call    esi
0x1001c323  pop     esi
0x1001c324  mov     eax, 0FFFFEC68h
0x1001c329  pop     edi
0x1001c32a  retn
```
