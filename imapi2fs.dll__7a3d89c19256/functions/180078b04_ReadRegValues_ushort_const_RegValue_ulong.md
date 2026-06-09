# ReadRegValues(ushort const *,RegValue *,ulong)

- ea: `0x180078b04`
- end: `0x180078dc4`
- name: `?ReadRegValues@@YA_NPEBGPEAURegValue@@K@Z`
- size: `704`
- prototype: `bool __fastcall(const unsigned __int16 *, struct RegValue *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x1800052c0`

## callees

- `0x180003f50`
- `0x180005040`
- `0x180028568`
- `0x180078b04`

## import_xrefs

- `ADVAPI32!RegQueryMultipleValuesW` at `0x180078c34`
- `ADVAPI32!RegQueryMultipleValuesW` at `0x180078c34`
- `ADVAPI32!RegCloseKey` at `0x180078da8`
- `ADVAPI32!RegCloseKey` at `0x180078da8`
- `ADVAPI32!RegOpenKeyExW` at `0x180078b4d`
- `ADVAPI32!RegOpenKeyExW` at `0x180078b4d`

## string_xrefs

- `0x180078b38`: `SYSTEM\CurrentControlSet\Services\imapi`

## pseudocode

```c
char __fastcall ReadRegValues(const unsigned __int16 *a1, struct RegValue *a2)
{
  WCHAR *v2; // rbp
  char v3; // si
  struct value_entW *v4; // rdi
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 i; // rdx
  __int64 v8; // rax
  __int64 v9; // rcx
  PVOID *v10; // r9
  __int64 j; // rsi
  __int64 v12; // rax
  __int64 v13; // rcx
  DWORD ve_type; // edx
  struct RegValue *v15; // rdx
  struct RegValue *v16; // rax
  unsigned int v17; // edx
  unsigned int v18; // eax
  HKEY hKey; // [rsp+58h] [rbp+10h] BYREF
  DWORD ldwTotsize; // [rsp+60h] [rbp+18h] BYREF

  v2 = 0;
  hKey = 0;
  ldwTotsize = 0;
  v3 = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\imapi", 0, 1u, &hKey) || !hKey )
  {
    v5 = WPP_GLOBAL_Control;
    v4 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 11;
      goto LABEL_39;
    }
  }
  else
  {
    v4 = (struct value_entW *)operator new(0x40u);
    if ( v4 )
    {
      v2 = (WCHAR *)operator new(0x10u);
      if ( v2 )
      {
        for ( i = 0; i != 2; ++i )
        {
          v8 = i;
          v9 = 160 * i;
          v4[v8].ve_valuename = (LPWSTR)((char *)&g_aFsiRegValues + v9);
        }
        ldwTotsize = 16;
        if ( RegQueryMultipleValuesW(hKey, v4, 2u, v2, &ldwTotsize) )
        {
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v6 = 14;
            goto LABEL_39;
          }
        }
        else
        {
          v10 = (PVOID *)WPP_GLOBAL_Control;
          for ( j = 0; j != 2; ++j )
          {
            v12 = j;
            v13 = 160 * j;
            ve_type = v4[j].ve_type;
            *((_DWORD *)&g_aFsiRegValues + 40 * j + 33) = ve_type;
            if ( ve_type == 4 )
            {
              v17 = *(_DWORD *)v4[v12].ve_valueptr;
              v18 = *(_DWORD *)((char *)&g_aFsiRegValues + v13 + 144);
              *(_DWORD *)((char *)&g_aFsiRegValues + v13 + 136) = v17;
              if ( v17 < v18 || (v18 = *(_DWORD *)((char *)&g_aFsiRegValues + v13 + 152), v17 > v18) )
                *(_DWORD *)((char *)&g_aFsiRegValues + v13 + 136) = v18;
            }
            else if ( ve_type == 11 )
            {
              v15 = *(struct RegValue **)v4[v12].ve_valueptr;
              v16 = *(struct RegValue near **)((char *)&g_aFsiRegValues + v13 + 144);
              *(struct RegValue near **)((char *)&g_aFsiRegValues + v13 + 136) = v15;
              if ( v15 < v16 || (v16 = *(struct RegValue near **)((char *)&g_aFsiRegValues + v13 + 152), v15 > v16) )
                *(struct RegValue near **)((char *)&g_aFsiRegValues + v13 + 136) = v16;
            }
            else if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 4) != 0 && *((_BYTE *)v10 + 25) >= 3u )
            {
              WPP_SF_(v10[2], 15, WPP_2e7f1749bc5c37a254c38076e514763e_Traceguids);
              v10 = (PVOID *)WPP_GLOBAL_Control;
            }
          }
          v3 = 1;
        }
      }
      else
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v6 = 13;
          goto LABEL_39;
        }
      }
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v6 = 12;
LABEL_39:
        WPP_SF_(v5[2], v6, WPP_2e7f1749bc5c37a254c38076e514763e_Traceguids);
      }
    }
  }
  operator delete(v2);
  operator delete(v4);
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x180078b04  mov     rax, rsp
0x180078b07  mov     [rax+8], rbx
0x180078b0b  mov     [rax+20h], rbp
0x180078b0f  mov     [rax+18h], r8d
0x180078b13  mov     [rax+10h], rdx
0x180078b17  push    rsi
0x180078b18  push    rdi
0x180078b19  push    r15
0x180078b1b  sub     rsp, 30h
0x180078b1f  xor     ebp, ebp
0x180078b21  mov     qword ptr [rax+10h], 0
0x180078b29  mov     [rax+18h], ebp
0x180078b2c  lea     rax, [rax+10h]
0x180078b30  xor     r8d, r8d; ulOptions
0x180078b33  mov     [rsp+48h+phkResult], rax; phkResult
0x180078b38  lea     rdx, ?g_szFsiRegKey@@3QBGB; "SYSTEM\\CurrentControlSet\\Services\\im"...
0x180078b3f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180078b46  lea     r9d, [rbp+1]; samDesired
0x180078b4a  xor     sil, sil
0x180078b4d  call    cs:__imp_RegOpenKeyExW
0x180078b53  test    eax, eax
0x180078b55  jnz     loc_180078D5A
0x180078b5b  cmp     [rsp+48h+hKey], rbp
0x180078b60  jz      loc_180078D5A
0x180078b66  lea     ecx, [rbp+40h]; unsigned __int64
0x180078b69  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180078b6e  mov     rdi, rax
0x180078b71  test    rax, rax
0x180078b74  jnz     short loc_180078BA9
0x180078b76  mov     rcx, cs:WPP_GLOBAL_Control
0x180078b7d  lea     rbx, WPP_GLOBAL_Control
0x180078b84  cmp     rcx, rbx
0x180078b87  jz      loc_180078D8E
0x180078b8d  test    byte ptr [rcx+1Ch], 4
0x180078b91  jz      loc_180078D8E
0x180078b97  cmp     byte ptr [rcx+19h], 2
0x180078b9b  jb      loc_180078D8E
0x180078ba1  lea     edx, [rbp+0Ch]
0x180078ba4  jmp     loc_180078D7E
0x180078ba9  mov     ebx, 10h
0x180078bae  mov     ecx, ebx; unsigned __int64
0x180078bb0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180078bb5  mov     rbp, rax
0x180078bb8  test    rax, rax
0x180078bbb  jnz     short loc_180078BF0
0x180078bbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180078bc4  lea     rbx, WPP_GLOBAL_Control
0x180078bcb  cmp     rcx, rbx
0x180078bce  jz      loc_180078D8E
0x180078bd4  test    byte ptr [rcx+1Ch], 4
0x180078bd8  jz      loc_180078D8E
0x180078bde  cmp     byte ptr [rcx+19h], 2
0x180078be2  jb      loc_180078D8E
0x180078be8  lea     edx, [rax+0Dh]
0x180078beb  jmp     loc_180078D7E
0x180078bf0  xor     edx, edx
0x180078bf2  lea     r15, ?g_aFsiRegValues@@3PAURegValue@@A; "MaxTrackedNonstashedItemCount"
0x180078bf9  lea     rcx, [rdx+rdx*4]
0x180078bfd  mov     rax, rdx
0x180078c00  shl     rcx, 5
0x180078c04  inc     rdx
0x180078c07  shl     rax, 5
0x180078c0b  add     rcx, r15
0x180078c0e  mov     [rax+rdi], rcx
0x180078c12  cmp     rdx, 2
0x180078c16  jnz     short loc_180078BF9
0x180078c18  mov     rcx, [rsp+48h+hKey]; hKey
0x180078c1d  lea     rax, [rsp+48h+ldwTotsize]
0x180078c22  mov     r8d, edx; num_vals
0x180078c25  mov     [rsp+48h+phkResult], rax; ldwTotsize
0x180078c2a  mov     rdx, rdi; val_list
0x180078c2d  mov     [rsp+48h+ldwTotsize], ebx
0x180078c31  mov     r9, rbp; lpValueBuf
0x180078c34  call    cs:__imp_RegQueryMultipleValuesW
0x180078c3a  test    eax, eax
0x180078c3c  jz      short loc_180078C73
0x180078c3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180078c45  lea     rbx, WPP_GLOBAL_Control
0x180078c4c  cmp     rcx, rbx
0x180078c4f  jz      loc_180078D8E
0x180078c55  test    byte ptr [rcx+1Ch], 4
0x180078c59  jz      loc_180078D8E
0x180078c5f  cmp     byte ptr [rcx+19h], 2
0x180078c63  jb      loc_180078D8E
0x180078c69  mov     edx, 0Eh
0x180078c6e  jmp     loc_180078D7E
0x180078c73  mov     r9, cs:WPP_GLOBAL_Control
0x180078c7a  lea     rbx, WPP_GLOBAL_Control
0x180078c81  xor     esi, esi
0x180078c83  mov     rax, rsi
0x180078c86  lea     rcx, [rsi+rsi*4]
0x180078c8a  shl     rax, 5
0x180078c8e  shl     rcx, 5
0x180078c92  mov     edx, [rax+rdi+18h]
0x180078c96  mov     [rcx+r15+84h], edx
0x180078c9e  cmp     edx, 4
0x180078ca1  jz      short loc_180078D19
0x180078ca3  cmp     edx, 0Bh
0x180078ca6  jz      short loc_180078CE5
0x180078ca8  cmp     r9, rbx
0x180078cab  jz      loc_180078D48
0x180078cb1  test    byte ptr [r9+1Ch], 4
0x180078cb6  jz      loc_180078D48
0x180078cbc  cmp     byte ptr [r9+19h], 3
0x180078cc1  jb      loc_180078D48
0x180078cc7  mov     rcx, [r9+10h]
0x180078ccb  lea     r8, WPP_2e7f1749bc5c37a254c38076e514763e_Traceguids
0x180078cd2  mov     edx, 0Fh
0x180078cd7  call    WPP_SF_
0x180078cdc  mov     r9, cs:WPP_GLOBAL_Control
0x180078ce3  jmp     short loc_180078D48
0x180078ce5  mov     rax, [rax+rdi+10h]
0x180078cea  mov     rdx, [rax]
0x180078ced  mov     rax, [rcx+r15+90h]
0x180078cf5  mov     [rcx+r15+88h], rdx
0x180078cfd  cmp     rdx, rax
0x180078d00  jb      short loc_180078D0F
0x180078d02  mov     rax, [rcx+r15+98h]
0x180078d0a  cmp     rdx, rax
0x180078d0d  jbe     short loc_180078D48
0x180078d0f  mov     [rcx+r15+88h], rax
0x180078d17  jmp     short loc_180078D48
0x180078d19  mov     rax, [rax+rdi+10h]
0x180078d1e  mov     edx, [rax]
0x180078d20  mov     eax, [rcx+r15+90h]
0x180078d28  mov     [rcx+r15+88h], edx
0x180078d30  cmp     edx, eax
0x180078d32  jb      short loc_180078D40
0x180078d34  mov     eax, [rcx+r15+98h]
0x180078d3c  cmp     edx, eax
0x180078d3e  jbe     short loc_180078D48
0x180078d40  mov     [rcx+r15+88h], eax
0x180078d48  inc     rsi
0x180078d4b  cmp     rsi, 2
0x180078d4f  jnz     loc_180078C83
0x180078d55  mov     sil, 1
0x180078d58  jmp     short loc_180078D8E
0x180078d5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180078d61  lea     rbx, WPP_GLOBAL_Control
0x180078d68  xor     edi, edi
0x180078d6a  cmp     rcx, rbx
0x180078d6d  jz      short loc_180078D8E
0x180078d6f  test    byte ptr [rcx+1Ch], 4
0x180078d73  jz      short loc_180078D8E
0x180078d75  cmp     byte ptr [rcx+19h], 2
0x180078d79  jb      short loc_180078D8E
0x180078d7b  lea     edx, [rdi+0Bh]
0x180078d7e  mov     rcx, [rcx+10h]
0x180078d82  lea     r8, WPP_2e7f1749bc5c37a254c38076e514763e_Traceguids
0x180078d89  call    WPP_SF_
0x180078d8e  mov     rcx, rbp; void *
0x180078d91  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180078d96  mov     rcx, rdi; void *
0x180078d99  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180078d9e  mov     rcx, [rsp+48h+hKey]; hKey
0x180078da3  test    rcx, rcx
0x180078da6  jz      short loc_180078DAE
0x180078da8  call    cs:__imp_RegCloseKey
0x180078dae  mov     rbx, [rsp+48h+arg_0]
0x180078db3  mov     al, sil
0x180078db6  mov     rbp, [rsp+48h+arg_18]
0x180078dbb  add     rsp, 30h
0x180078dbf  pop     r15
0x180078dc1  pop     rdi
0x180078dc2  pop     rsi
0x180078dc3  retn
```
