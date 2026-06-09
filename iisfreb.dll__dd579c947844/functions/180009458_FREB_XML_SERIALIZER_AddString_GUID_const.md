# FREB_XML_SERIALIZER::AddString(_GUID const *)

- ea: `0x180009458`
- end: `0x1800094b5`
- name: `?AddString@FREB_XML_SERIALIZER@@QEAAXPEBU_GUID@@@Z`
- size: `93`
- prototype: `void(FREB_XML_SERIALIZER *__hidden this, const struct _GUID *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180004ae4`
- `0x180009948`

## callees

- `0x180009458`
- `0x180009690`
- `0x180009734`

## pseudocode

```c
void __fastcall FREB_XML_SERIALIZER::AddString(FREB_XML_SERIALIZER *this, const struct _GUID *a2)
{
  char *Memory; // rax
  int v5; // eax
  unsigned int v6; // [rsp+30h] [rbp+8h] BYREF

  if ( !*((_DWORD *)this + 7) )
  {
    Memory = FREB_XML_SERIALIZER::AllocateMemory(this, 0x27u);
    if ( Memory )
    {
      v6 = 39;
      v5 = FREB_XML_SERIALIZER::ConvertCLSIDToString(a2, Memory, &v6);
      if ( v5 >= 0 )
        --*((_DWORD *)this + 6);
      else
        *((_DWORD *)this + 7) = v5;
    }
    else
    {
      *((_DWORD *)this + 7) = -2147024888;
    }
  }
}

```

## disassembly

```asm
0x180009458  mov     [rsp+arg_8], rbx
0x18000945d  push    rdi
0x18000945e  sub     rsp, 20h
0x180009462  cmp     dword ptr [rcx+1Ch], 0
0x180009466  mov     rdi, rdx
0x180009469  mov     rbx, rcx
0x18000946c  jnz     short loc_1800094AA
0x18000946e  mov     edx, 27h ; '''; unsigned int
0x180009473  call    ?AllocateMemory@FREB_XML_SERIALIZER@@QEAAPEAEK@Z; FREB_XML_SERIALIZER::AllocateMemory(ulong)
0x180009478  test    rax, rax
0x18000947b  jnz     short loc_180009486
0x18000947d  mov     dword ptr [rbx+1Ch], 80070008h
0x180009484  jmp     short loc_1800094AA
0x180009486  lea     r8, [rsp+28h+arg_0]; unsigned int *
0x18000948b  mov     [rsp+28h+arg_0], 27h ; '''
0x180009493  mov     rdx, rax; char *
0x180009496  mov     rcx, rdi; struct _GUID *
0x180009499  call    ?ConvertCLSIDToString@FREB_XML_SERIALIZER@@SAJPEBU_GUID@@PEADPEAK@Z; FREB_XML_SERIALIZER::ConvertCLSIDToString(_GUID const *,char *,ulong *)
0x18000949e  test    eax, eax
0x1800094a0  jns     short loc_1800094A7
0x1800094a2  mov     [rbx+1Ch], eax
0x1800094a5  jmp     short loc_1800094AA
0x1800094a7  dec     dword ptr [rbx+18h]
0x1800094aa  mov     rbx, [rsp+28h+arg_8]
0x1800094af  add     rsp, 20h
0x1800094b3  pop     rdi
0x1800094b4  retn
```
