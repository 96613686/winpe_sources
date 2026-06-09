# CONFIG_CACHE::GetDesiredManagedRuntimeVersion(STRU *,int *,PARSE_ERROR_INFO *)

- ea: `0x18004eda8`
- end: `0x18004ee42`
- name: `?GetDesiredManagedRuntimeVersion@CONFIG_CACHE@@AEAAJPEAVSTRU@@PEAHPEAVPARSE_ERROR_INFO@@@Z`
- size: `154`
- prototype: `int(CONFIG_CACHE *__hidden this, struct STRU *, int *, struct PARSE_ERROR_INFO *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x180002b20`

## callees

- `0x18004e2d8`
- `0x18004eda8`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004ee03`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004ee24`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004ee03`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18004ee24`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18004ede1`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18004ee10`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18004ede1`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18004ee10`

## pseudocode

```c
int __fastcall CONFIG_CACHE::GetDesiredManagedRuntimeVersion(
        CONFIG_CACHE *this,
        struct STRU *a2,
        int *a3,
        struct PARSE_ERROR_INFO *a4)
{
  int result; // eax
  const unsigned __int16 *v7; // rdx
  int v8; // eax
  int v9; // ecx

  if ( (unsigned int)(*((_DWORD *)this + 94) - 4) > 0xFFFFFFFA
    || (result = CONFIG_CACHE::GetAppManagedRuntimeVersion(this, (CONFIG_CACHE *)((char *)this + 352), a2, a3, a4),
        result >= 0) )
  {
    if ( !STRU::IsEmpty(a2) )
      goto LABEL_14;
    v7 = &szDomain;
    if ( *((_QWORD *)this + 97) )
      v7 = (const unsigned __int16 *)*((_QWORD *)this + 97);
    result = STRU::Copy(a2, v7);
    if ( result >= 0 )
    {
LABEL_14:
      if ( STRU::IsEmpty(a2) )
      {
        v8 = STRU::Copy(a2, L"v4.0");
        v9 = 0;
        if ( v8 < 0 )
          return v8;
        return v9;
      }
      else
      {
        return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004eda8  mov     [rsp+arg_0], rbx
0x18004edad  push    rdi
0x18004edae  sub     rsp, 30h
0x18004edb2  mov     rbx, rdx
0x18004edb5  mov     rdi, rcx
0x18004edb8  lea     rdx, [rcx+160h]; struct PATH *
0x18004edbf  mov     eax, [rdx+18h]
0x18004edc2  sub     eax, 4
0x18004edc5  cmp     eax, 0FFFFFFFAh
0x18004edc8  ja      short loc_18004EDDE
0x18004edca  mov     [rsp+38h+var_18], r9; struct PARSE_ERROR_INFO *
0x18004edcf  mov     r9, r8; int *
0x18004edd2  mov     r8, rbx; struct STRU *
0x18004edd5  call    ?GetAppManagedRuntimeVersion@CONFIG_CACHE@@AEAAJPEAVPATH@@PEAVSTRU@@PEAHPEAVPARSE_ERROR_INFO@@@Z; CONFIG_CACHE::GetAppManagedRuntimeVersion(PATH *,STRU *,int *,PARSE_ERROR_INFO *)
0x18004edda  test    eax, eax
0x18004eddc  js      short loc_18004EE37
0x18004edde  mov     rcx, rbx
0x18004ede1  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x18004ede7  test    al, al
0x18004ede9  jz      short loc_18004EE0D
0x18004edeb  mov     rax, [rdi+308h]
0x18004edf2  lea     rdx, szDomain
0x18004edf9  test    rax, rax
0x18004edfc  mov     rcx, rbx
0x18004edff  cmovnz  rdx, rax
0x18004ee03  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18004ee09  test    eax, eax
0x18004ee0b  js      short loc_18004EE37
0x18004ee0d  mov     rcx, rbx
0x18004ee10  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x18004ee16  test    al, al
0x18004ee18  jz      short loc_18004EE35
0x18004ee1a  lea     rdx, aV40; "v4.0"
0x18004ee21  mov     rcx, rbx
0x18004ee24  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18004ee2a  xor     ecx, ecx
0x18004ee2c  test    eax, eax
0x18004ee2e  cmovs   ecx, eax
0x18004ee31  mov     eax, ecx
0x18004ee33  jmp     short loc_18004EE37
0x18004ee35  xor     eax, eax
0x18004ee37  mov     rbx, [rsp+38h+arg_0]
0x18004ee3c  add     rsp, 30h
0x18004ee40  pop     rdi
0x18004ee41  retn
```
