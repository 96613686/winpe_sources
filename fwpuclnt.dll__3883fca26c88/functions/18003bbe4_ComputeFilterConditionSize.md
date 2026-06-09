# ComputeFilterConditionSize

- ea: `0x18003bbe4`
- end: `0x18003bcc1`
- name: `ComputeFilterConditionSize`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003bcc8`

## callees

- `0x18003bbe4`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x18003bc4e`
- `ntdll!RtlSubAuthorityCountSid` at `0x18003bc4e`

## pseudocode

```c
__int64 __fastcall ComputeFilterConditionSize(__int64 a1)
{
  __int64 v2; // r8
  __int64 v3; // rcx
  int v4; // edx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v10; // edx
  int v11; // edx
  int v12; // edx
  int v13; // edx
  _WORD *v14; // rax
  __int64 v15; // rcx

  v2 = 16;
  v3 = a1 + 8;
  v4 = *(_DWORD *)v3;
  if ( *(_DWORD *)v3 == 258 )
  {
    v3 = *(_QWORD *)(a1 + 16);
    v4 = *(_DWORD *)v3;
  }
  if ( v4 > 13 )
  {
    v10 = v4 - 14;
    if ( !v10 )
    {
LABEL_10:
      v2 = **(unsigned int **)(v3 + 8) + 24LL;
      return v2 + 24;
    }
    v11 = v10 - 3;
    if ( !v11 )
    {
      v14 = *(_WORD **)(v3 + 8);
      if ( v14 )
      {
        v15 = 0x7FFFFFFF;
        do
        {
          if ( !*v14 )
            break;
          ++v14;
          --v15;
        }
        while ( v15 );
        if ( v15 )
          v2 = MEMORY[0] + 16LL;
      }
      return v2 + 24;
    }
    v12 = v11 - 1;
    if ( !v12 )
    {
      v2 = 22;
      return v2 + 24;
    }
    v13 = v12 - 238;
    if ( v13 )
    {
      if ( v13 == 1 )
        v2 = 33;
      return v2 + 24;
    }
LABEL_13:
    v2 = 24;
    return v2 + 24;
  }
  if ( v4 == 13 )
  {
    v2 = 4LL * *RtlSubAuthorityCountSid(*(PSID *)(v3 + 8)) + 22;
    return v2 + 24;
  }
  v5 = v4 - 4;
  if ( !v5 )
    goto LABEL_13;
  v6 = v5 - 4;
  if ( !v6 )
    goto LABEL_13;
  v7 = v6 - 2;
  if ( !v7 )
    goto LABEL_13;
  v8 = v7 - 1;
  if ( !v8 )
  {
    v2 = 32;
    return v2 + 24;
  }
  if ( v8 == 1 )
    goto LABEL_10;
  return v2 + 24;
}

```

## disassembly

```asm
0x18003bbe4  sub     rsp, 28h
0x18003bbe8  mov     rax, rcx
0x18003bbeb  mov     r8d, 10h
0x18003bbf1  add     rcx, 8
0x18003bbf5  mov     edx, [rcx]
0x18003bbf7  cmp     edx, 102h
0x18003bbfd  jnz     short loc_18003BC05
0x18003bbff  mov     rcx, [rax+10h]
0x18003bc03  mov     edx, [rcx]
0x18003bc05  cmp     edx, 0Dh
0x18003bc08  jg      short loc_18003BC67
0x18003bc0a  jz      short loc_18003BC4A
0x18003bc0c  sub     edx, 4
0x18003bc0f  jz      short loc_18003BC42
0x18003bc11  sub     edx, 4
0x18003bc14  jz      short loc_18003BC42
0x18003bc16  sub     edx, 2
0x18003bc19  jz      short loc_18003BC42
0x18003bc1b  sub     edx, 1
0x18003bc1e  jz      short loc_18003BC3A
0x18003bc20  cmp     edx, 1
0x18003bc23  jnz     short loc_18003BC30
0x18003bc25  mov     rax, [rcx+8]
0x18003bc29  mov     r8d, [rax]
0x18003bc2c  add     r8, 18h
0x18003bc30  lea     rax, [r8+18h]
0x18003bc34  add     rsp, 28h
0x18003bc38  retn
0x18003bc3a  mov     r8d, 20h ; ' '
0x18003bc40  jmp     short loc_18003BC30
0x18003bc42  mov     r8d, 18h
0x18003bc48  jmp     short loc_18003BC30
0x18003bc4a  mov     rcx, [rcx+8]; Sid
0x18003bc4e  call    cs:__imp_RtlSubAuthorityCountSid
0x18003bc55  nop     dword ptr [rax+rax+00h]
0x18003bc5a  movzx   ecx, byte ptr [rax]
0x18003bc5d  lea     r8, ds:16h[rcx*4]
0x18003bc65  jmp     short loc_18003BC30
0x18003bc67  sub     edx, 0Eh
0x18003bc6a  jz      short loc_18003BC25
0x18003bc6c  sub     edx, 3
0x18003bc6f  jz      short loc_18003BC91
0x18003bc71  sub     edx, 1
0x18003bc74  jz      short loc_18003BC89
0x18003bc76  sub     edx, 0EEh
0x18003bc7c  jz      short loc_18003BC42
0x18003bc7e  cmp     edx, 1
0x18003bc81  jnz     short loc_18003BC30
0x18003bc83  lea     r8d, [rdx+20h]
0x18003bc87  jmp     short loc_18003BC30
0x18003bc89  mov     r8d, 16h
0x18003bc8f  jmp     short loc_18003BC30
0x18003bc91  mov     rax, [rcx+8]
0x18003bc95  xor     edx, edx
0x18003bc97  test    rax, rax
0x18003bc9a  jz      short loc_18003BC30
0x18003bc9c  mov     ecx, 7FFFFFFFh
0x18003bca1  cmp     [rax], dx
0x18003bca4  jz      short loc_18003BCB0
0x18003bca6  add     rax, 2
0x18003bcaa  sub     rcx, 1
0x18003bcae  jnz     short loc_18003BCA1
0x18003bcb0  test    rcx, rcx
0x18003bcb3  jz      loc_18003BC30
0x18003bcb9  add     r8, [rdx]
0x18003bcbc  jmp     loc_18003BC30
```
