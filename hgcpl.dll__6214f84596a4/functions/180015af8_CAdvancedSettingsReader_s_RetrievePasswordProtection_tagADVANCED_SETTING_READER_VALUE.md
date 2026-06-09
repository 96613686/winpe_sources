# CAdvancedSettingsReader::_s_RetrievePasswordProtection(tagADVANCED_SETTING_READER_VALUE *)

- ea: `0x180015af8`
- end: `0x180015b8f`
- name: `?_s_RetrievePasswordProtection@CAdvancedSettingsReader@@CAXPEAUtagADVANCED_SETTING_READER_VALUE@@@Z`
- size: `151`
- prototype: `void __fastcall(struct tagADVANCED_SETTING_READER_VALUE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180013368`

## callees

- `0x1800130dc`
- `0x180015af8`

## import_xrefs

- `SHLWAPI!__imp_IsOS` at `0x180015b06`
- `SHLWAPI!__imp_IsOS` at `0x180015b06`

## pseudocode

```c
void __fastcall CAdvancedSettingsReader::_s_RetrievePasswordProtection(struct tagADVANCED_SETTING_READER_VALUE *a1)
{
  int v2; // edx
  unsigned int v3; // r9d
  unsigned int i; // r8d
  __int64 v5; // rax
  unsigned int v6; // r9d
  unsigned int v7; // r8d

  if ( IsOS(0x1Cu) )
    v2 = 0;
  else
    v2 = ((unsigned int)IsGuestAccountEnabled() != 0) + 1;
  v3 = 0;
  for ( i = 1; i < 3; ++i )
  {
    if ( *((_DWORD *)qword_18001EB90 + 3 * i) == v2 )
    {
      v3 = i;
      break;
    }
  }
  v5 = v3;
  v6 = 0;
  v7 = 1;
  *(_DWORD *)a1 = *((_DWORD *)&qword_18001EB90[1] + 3 * v5);
  while ( v7 < 3 )
  {
    if ( *((_DWORD *)qword_18001EB90 + 3 * v7) == v2 )
    {
      v6 = v7;
      break;
    }
    ++v7;
  }
  *((_DWORD *)a1 + 1) = *((_DWORD *)qword_18001EB90 + 3 * v6 + 1);
}

```

## disassembly

```asm
0x180015af8  push    rbx
0x180015afa  sub     rsp, 20h
0x180015afe  mov     rbx, rcx
0x180015b01  mov     ecx, 1Ch; dwOS
0x180015b06  call    cs:__imp_IsOS
0x180015b0c  test    eax, eax
0x180015b0e  jz      short loc_180015B14
0x180015b10  xor     edx, edx
0x180015b12  jmp     short loc_180015B21
0x180015b14  call    ?IsGuestAccountEnabled@@YAHK@Z; IsGuestAccountEnabled(ulong)
0x180015b19  neg     eax
0x180015b1b  sbb     edx, edx
0x180015b1d  neg     edx
0x180015b1f  inc     edx
0x180015b21  xor     r9d, r9d
0x180015b24  lea     r10, qword_18001EB90
0x180015b2b  lea     r8d, [r9+1]
0x180015b2f  cmp     r8d, 3
0x180015b33  jnb     short loc_180015B4A
0x180015b35  mov     eax, r8d
0x180015b38  lea     rcx, [rax+rax*2]
0x180015b3c  cmp     [r10+rcx*4], edx
0x180015b40  jz      short loc_180015B47
0x180015b42  inc     r8d
0x180015b45  jmp     short loc_180015B2F
0x180015b47  mov     r9d, r8d
0x180015b4a  mov     eax, r9d
0x180015b4d  xor     r9d, r9d
0x180015b50  lea     rax, [rax+rax*2]
0x180015b54  mov     eax, [r10+rax*4+8]
0x180015b59  lea     r8d, [r9+1]
0x180015b5d  mov     [rbx], eax
0x180015b5f  cmp     r8d, 3
0x180015b63  jnb     short loc_180015B7A
0x180015b65  mov     eax, r8d
0x180015b68  lea     rcx, [rax+rax*2]
0x180015b6c  cmp     [r10+rcx*4], edx
0x180015b70  jz      short loc_180015B77
0x180015b72  inc     r8d
0x180015b75  jmp     short loc_180015B5F
0x180015b77  mov     r9d, r8d
0x180015b7a  mov     eax, r9d
0x180015b7d  lea     rax, [rax+rax*2]
0x180015b81  mov     eax, [r10+rax*4+4]
0x180015b86  mov     [rbx+4], eax
0x180015b89  add     rsp, 20h
0x180015b8d  pop     rbx
0x180015b8e  retn
```
