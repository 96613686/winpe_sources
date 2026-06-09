# CValue::Compare(CValue *)

- ea: `0x18000a7f4`
- end: `0x18000a8b4`
- name: `?Compare@CValue@@QEAAHPEAV1@@Z`
- size: `192`
- prototype: `__int64 __fastcall(CValue *__hidden this, struct CValue *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008f28`
- `0x18000a410`

## callees

- `0x18000a7f4`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18000a84b`

## pseudocode

```c
int __fastcall CValue::Compare(CValue *this, struct CValue *a2)
{
  int v3; // eax
  int result; // eax
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  const WCHAR *v9; // rcx
  const WCHAR *v10; // rdx
  unsigned int v11; // eax
  bool v12; // cf
  bool v13; // zf
  unsigned __int16 v14; // ax
  int v15; // r9d
  bool v16; // cc
  __int16 v17; // r9
  __int16 v18; // dx

  v3 = *((_DWORD *)a2 + 4);
  if ( !*((_DWORD *)this + 4) )
  {
    if ( v3 )
      return -1;
    return 0;
  }
  if ( !v3 )
    return 1;
  v5 = *((_DWORD *)this + 1) - 1;
  if ( v5 )
  {
    v6 = v5 - 1;
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( v7 )
      {
        v8 = v7 - 1;
        if ( v8 )
        {
          if ( (unsigned int)(v8 - 1) <= 1 )
          {
            v9 = (const WCHAR *)*((_QWORD *)this + 4);
            if ( v9 && (v10 = (const WCHAR *)*((_QWORD *)a2 + 4)) != 0 )
              return lstrcmpW(v9, v10);
            else
              return -2;
          }
          return 1;
        }
        v11 = *((_DWORD *)this + 8);
        v12 = v11 < *((_DWORD *)a2 + 8);
        v13 = v11 == *((_DWORD *)a2 + 8);
      }
      else
      {
        v14 = *((_WORD *)this + 16);
        v12 = v14 < *((_WORD *)a2 + 16);
        v13 = v14 == *((_WORD *)a2 + 16);
      }
      if ( !v13 )
        return v12 ? -1 : 1;
      return 0;
    }
    v15 = *((_DWORD *)this + 8);
    if ( v15 != *((_DWORD *)a2 + 8) )
    {
      result = -1;
      v16 = v15 < *((_DWORD *)a2 + 8);
      goto LABEL_20;
    }
    return 0;
  }
  v17 = *((_WORD *)a2 + 16);
  v18 = *((_WORD *)this + 16);
  if ( v18 == v17 )
    return 0;
  result = -1;
  v16 = v18 < v17;
LABEL_20:
  if ( !v16 )
    return 1;
  return result;
}

```

## disassembly

```asm
0x18000a7f4  cmp     dword ptr [rcx+10h], 0
0x18000a7f8  mov     r8, rcx
0x18000a7fb  mov     eax, [rdx+10h]
0x18000a7fe  jnz     short loc_18000A810
0x18000a800  test    eax, eax
0x18000a802  jz      loc_18000A8A1
0x18000a808  or      eax, 0FFFFFFFFh
0x18000a80b  jmp     locret_18000A8B3
0x18000a810  test    eax, eax
0x18000a812  jz      loc_18000A8AE
0x18000a818  mov     ecx, [rcx+4]
0x18000a81b  sub     ecx, 1
0x18000a81e  jz      short loc_18000A891
0x18000a820  sub     ecx, 1
0x18000a823  jz      short loc_18000A876
0x18000a825  sub     ecx, 1
0x18000a828  jz      short loc_18000A862
0x18000a82a  sub     ecx, 1
0x18000a82d  jz      short loc_18000A859
0x18000a82f  sub     ecx, 1
0x18000a832  jz      short loc_18000A839
0x18000a834  sub     ecx, 1
0x18000a837  jnz     short loc_18000A8AE
0x18000a839  mov     rcx, [r8+20h]
0x18000a83d  test    rcx, rcx
0x18000a840  jz      short loc_18000A852
0x18000a842  mov     rdx, [rdx+20h]
0x18000a846  test    rdx, rdx
0x18000a849  jz      short loc_18000A852
0x18000a84b  jmp     cs:__imp_lstrcmpW
0x18000a852  mov     eax, 0FFFFFFFEh
0x18000a857  jmp     short locret_18000A8B3
0x18000a859  mov     eax, [r8+20h]
0x18000a85d  cmp     eax, [rdx+20h]
0x18000a860  jmp     short loc_18000A86B
0x18000a862  movzx   eax, word ptr [r8+20h]
0x18000a867  cmp     ax, [rdx+20h]
0x18000a86b  jz      short loc_18000A8A1
0x18000a86d  sbb     eax, eax
0x18000a86f  and     eax, 0FFFFFFFEh
0x18000a872  inc     eax
0x18000a874  jmp     short locret_18000A8B3
0x18000a876  mov     r9d, [r8+20h]
0x18000a87a  cmp     r9d, [rdx+20h]
0x18000a87e  jz      short loc_18000A8A1
0x18000a880  or      eax, 0FFFFFFFFh
0x18000a883  cmp     r9d, [rdx+20h]
0x18000a887  mov     ecx, 1
0x18000a88c  cmovge  eax, ecx
0x18000a88f  jmp     short locret_18000A8B3
0x18000a891  movzx   r9d, word ptr [rdx+20h]
0x18000a896  movzx   edx, word ptr [r8+20h]
0x18000a89b  cmp     dx, r9w
0x18000a89f  jnz     short loc_18000A8A5
0x18000a8a1  xor     eax, eax
0x18000a8a3  jmp     short locret_18000A8B3
0x18000a8a5  or      eax, 0FFFFFFFFh
0x18000a8a8  cmp     dx, r9w
0x18000a8ac  jmp     short loc_18000A887
0x18000a8ae  mov     eax, 1
0x18000a8b3  retn
```
