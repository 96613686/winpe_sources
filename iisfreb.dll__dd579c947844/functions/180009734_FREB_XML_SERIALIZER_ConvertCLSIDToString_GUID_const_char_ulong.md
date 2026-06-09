# FREB_XML_SERIALIZER::ConvertCLSIDToString(_GUID const *,char *,ulong *)

- ea: `0x180009734`
- end: `0x1800097bc`
- name: `?ConvertCLSIDToString@FREB_XML_SERIALIZER@@SAJPEBU_GUID@@PEADPEAK@Z`
- size: `136`
- prototype: `__int64 __fastcall(const struct _GUID *, char *, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180005210`
- `0x180009458`

## callees

- `0x180009734`

## pseudocode

```c
__int64 __fastcall FREB_XML_SERIALIZER::ConvertCLSIDToString(const struct _GUID *a1, char *a2, unsigned int *a3)
{
  __int64 result; // rax
  char *v5; // r8
  __int64 i; // r9
  __int64 v7; // rax

  if ( *a3 >= 0x27 )
  {
    *a2 = 123;
    v5 = a2 + 1;
    for ( i = 0; i != 20; ++i )
    {
      v7 = *((unsigned __int8 *)qword_18000ED20 + i);
      if ( (_BYTE)v7 == 45 )
      {
        *v5 = 45;
      }
      else
      {
        *v5 = a0123456789abcd[(unsigned __int64)*((unsigned __int8 *)&a1->Data1 + v7) >> 4];
        *++v5 = a0123456789abcd[*((_BYTE *)&a1->Data1 + v7) & 0xF];
      }
      ++v5;
    }
    *(_WORD *)v5 = 125;
    result = 0;
  }
  else
  {
    result = 2147942522LL;
  }
  *a3 = 39;
  return result;
}

```

## disassembly

```asm
0x180009734  mov     [rsp+arg_0], rbx
0x180009739  cmp     dword ptr [r8], 27h ; '''
0x18000973d  mov     r10, r8
0x180009740  mov     r11, rcx
0x180009743  jnb     short loc_18000974C
0x180009745  mov     eax, 8007007Ah
0x18000974a  jmp     short loc_1800097AF
0x18000974c  mov     byte ptr [rdx], 7Bh ; '{'
0x18000974f  lea     r8, [rdx+1]
0x180009753  xor     r9d, r9d
0x180009756  lea     rbx, __ImageBase
0x18000975d  movzx   eax, byte ptr [r9+rbx+0ED20h]
0x180009766  cmp     al, 2Dh ; '-'
0x180009768  jnz     short loc_18000976F
0x18000976a  mov     [r8], al
0x18000976d  jmp     short loc_18000979B
0x18000976f  mov     rcx, rax
0x180009772  movzx   eax, byte ptr [rax+r11]
0x180009777  shr     rax, 4
0x18000977b  mov     al, [rax+rbx+0ED00h]
0x180009782  mov     [r8], al
0x180009785  movzx   eax, byte ptr [rcx+r11]
0x18000978a  and     eax, 0Fh
0x18000978d  mov     al, [rax+rbx+0ED00h]
0x180009794  mov     [r8+1], al
0x180009798  inc     r8
0x18000979b  inc     r8
0x18000979e  inc     r9
0x1800097a1  cmp     r9, 14h
0x1800097a5  jnz     short loc_18000975D
0x1800097a7  mov     word ptr [r8], 7Dh ; '}'
0x1800097ad  xor     eax, eax
0x1800097af  mov     rbx, [rsp+arg_0]
0x1800097b4  mov     dword ptr [r10], 27h ; '''
0x1800097bb  retn
```
