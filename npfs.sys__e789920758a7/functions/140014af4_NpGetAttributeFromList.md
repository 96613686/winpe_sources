# NpGetAttributeFromList

- ea: `0x140014af4`
- end: `0x140014bcd`
- name: `NpGetAttributeFromList`
- size: `217`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400156e8`

## callees

- `0x140014af4`

## string_xrefs

- `0x140014b70`: `ServerProcessId`
- `0x140014b4c`: `ClientComputerName`
- `0x140014b5e`: `ClientProcessId`
- `0x140014b43`: `RestrictedAccess`

## pseudocode

```c
__int64 __fastcall NpGetAttributeFromList(_QWORD *a1, unsigned __int64 a2, _QWORD *a3, _QWORD *a4)
{
  _QWORD *v4; // r10
  bool v8; // zf
  const char *v9; // rdx
  unsigned __int64 v10; // r8
  int v11; // ecx
  int v12; // eax
  _QWORD *v14; // rax

  v4 = (_QWORD *)*a1;
  if ( (_QWORD *)*a1 == a1 )
    return 3221226021LL;
  while ( 1 )
  {
    if ( a2 >= 8 )
    {
      v9 = (const char *)v4[2];
      if ( (_DWORD)v9 == 1 )
      {
        v9 = "ServerProcessId";
      }
      else
      {
        switch ( (unsigned int)v4[2] )
        {
          case 2u:
            v9 = "ServerSessionId";
            break;
          case 3u:
            v9 = "ClientProcessId";
            break;
          case 4u:
            v9 = "ClientSessionId";
            break;
          case 6u:
            v9 = "ClientComputerName";
            break;
          case 7u:
            v9 = "RestrictedAccess";
            break;
        }
      }
      v10 = a2 - (_QWORD)v9;
      do
      {
        v11 = (unsigned __int8)v9[v10];
        v12 = *(unsigned __int8 *)v9 - v11;
        if ( v12 )
          break;
        ++v9;
      }
      while ( v11 );
      v8 = v12 == 0;
    }
    else
    {
      v8 = v4[2] == a2;
    }
    if ( v8 )
      break;
    v4 = (_QWORD *)*v4;
    if ( v4 == a1 )
      return 3221226021LL;
  }
  v14 = v4 + 4;
  if ( v4[3] > 8u )
    v14 = (_QWORD *)*v14;
  *a3 = v14;
  *a4 = v4[3];
  return 0;
}

```

## disassembly

```asm
0x140014af4  mov     [rsp+arg_0], rbx
0x140014af9  mov     [rsp+arg_8], rdi
0x140014afe  mov     r10, [rcx]
0x140014b01  mov     rdi, r8
0x140014b04  mov     r11, rdx
0x140014b07  mov     rbx, rcx
0x140014b0a  cmp     r10, rcx
0x140014b0d  jz      loc_140014BA0
0x140014b13  cmp     r11, 8
0x140014b17  jnb     short loc_140014B1F
0x140014b19  cmp     [r10+10h], r11
0x140014b1d  jmp     short loc_140014B92
0x140014b1f  mov     rdx, [r10+10h]
0x140014b23  mov     ecx, edx
0x140014b25  sub     ecx, 1
0x140014b28  jz      short loc_140014B70
0x140014b2a  sub     ecx, 1
0x140014b2d  jz      short loc_140014B67
0x140014b2f  sub     ecx, 1
0x140014b32  jz      short loc_140014B5E
0x140014b34  sub     ecx, 1
0x140014b37  jz      short loc_140014B55
0x140014b39  sub     ecx, 2
0x140014b3c  jz      short loc_140014B4C
0x140014b3e  cmp     ecx, 1
0x140014b41  jnz     short loc_140014B77
0x140014b43  lea     rdx, aRestrictedacce; "RestrictedAccess"
0x140014b4a  jmp     short loc_140014B77
0x140014b4c  lea     rdx, Str2; "ClientComputerName"
0x140014b53  jmp     short loc_140014B77
0x140014b55  lea     rdx, aClientsessioni; "ClientSessionId"
0x140014b5c  jmp     short loc_140014B77
0x140014b5e  lea     rdx, aClientprocessi; "ClientProcessId"
0x140014b65  jmp     short loc_140014B77
0x140014b67  lea     rdx, aServersessioni; "ServerSessionId"
0x140014b6e  jmp     short loc_140014B77
0x140014b70  lea     rdx, aServerprocessi; "ServerProcessId"
0x140014b77  mov     r8, r11
0x140014b7a  sub     r8, rdx
0x140014b7d  movzx   eax, byte ptr [rdx]
0x140014b80  movzx   ecx, byte ptr [rdx+r8]
0x140014b85  sub     eax, ecx
0x140014b87  jnz     short loc_140014B90
0x140014b89  inc     rdx
0x140014b8c  test    ecx, ecx
0x140014b8e  jnz     short loc_140014B7D
0x140014b90  test    eax, eax
0x140014b92  jz      short loc_140014BB1
0x140014b94  mov     r10, [r10]
0x140014b97  cmp     r10, rbx
0x140014b9a  jnz     loc_140014B13
0x140014ba0  mov     eax, 0C0000225h
0x140014ba5  mov     rbx, [rsp+arg_0]
0x140014baa  mov     rdi, [rsp+arg_8]
0x140014baf  retn
0x140014bb1  cmp     qword ptr [r10+18h], 8
0x140014bb6  lea     rax, [r10+20h]
0x140014bba  jbe     short loc_140014BBF
0x140014bbc  mov     rax, [rax]
0x140014bbf  mov     [rdi], rax
0x140014bc2  mov     rax, [r10+18h]
0x140014bc6  mov     [r9], rax
0x140014bc9  xor     eax, eax
0x140014bcb  jmp     short loc_140014BA5
```
