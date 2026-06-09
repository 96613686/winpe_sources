# CNfsWmiV2ServerConfig::SetAllProtocol(ulong)

- ea: `0x180032cb0`
- end: `0x180032d61`
- name: `?SetAllProtocol@CNfsWmiV2ServerConfig@@UEAAJK@Z`
- size: `177`
- prototype: `__int64 __fastcall(CNfsWmiV2ServerConfig *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180032cb0`
- `0x180032f98`

## string_xrefs

- `0x180032d31`: `MapsvrProtocol`
- `0x180032cbf`: `MountProtocol`
- `0x180032cd9`: `NfsProtocol`
- `0x180032cef`: `NisProtocol`
- `0x180032d05`: `NlmProtocol`
- `0x180032d1b`: `NsmProtocol`
- `0x180032d47`: `PortmapProtocol`

## pseudocode

```c
int __fastcall CNfsWmiV2ServerConfig::SetAllProtocol(CNfsWmiV2ServerConfig *this, unsigned int a2)
{
  int result; // eax

  result = CNfsWmiV2ServerConfig::SetProtocol(this, L"MountProtocol", a2);
  if ( result >= 0 )
  {
    result = CNfsWmiV2ServerConfig::SetProtocol(this, L"NfsProtocol", a2);
    if ( result >= 0 )
    {
      result = CNfsWmiV2ServerConfig::SetProtocol(this, L"NisProtocol", a2);
      if ( result >= 0 )
      {
        result = CNfsWmiV2ServerConfig::SetProtocol(this, L"NlmProtocol", a2);
        if ( result >= 0 )
        {
          result = CNfsWmiV2ServerConfig::SetProtocol(this, L"NsmProtocol", a2);
          if ( result >= 0 )
          {
            result = CNfsWmiV2ServerConfig::SetProtocol(this, L"MapsvrProtocol", a2);
            if ( result >= 0 )
              return CNfsWmiV2ServerConfig::SetProtocol(this, L"PortmapProtocol", a2);
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180032cb0  mov     [rsp+arg_0], rbx
0x180032cb5  push    rdi
0x180032cb6  sub     rsp, 20h
0x180032cba  mov     ebx, edx
0x180032cbc  mov     r8d, edx; unsigned int
0x180032cbf  lea     rdx, aMountprotocol; "MountProtocol"
0x180032cc6  mov     rdi, rcx
0x180032cc9  call    ?SetProtocol@CNfsWmiV2ServerConfig@@AEAAJPEAGK@Z; CNfsWmiV2ServerConfig::SetProtocol(ushort *,ulong)
0x180032cce  test    eax, eax
0x180032cd0  js      loc_180032D56
0x180032cd6  mov     r8d, ebx; unsigned int
0x180032cd9  lea     rdx, aNfsprotocol; "NfsProtocol"
0x180032ce0  mov     rcx, rdi; this
0x180032ce3  call    ?SetProtocol@CNfsWmiV2ServerConfig@@AEAAJPEAGK@Z; CNfsWmiV2ServerConfig::SetProtocol(ushort *,ulong)
0x180032ce8  test    eax, eax
0x180032cea  js      short loc_180032D56
0x180032cec  mov     r8d, ebx; unsigned int
0x180032cef  lea     rdx, aNisprotocol; "NisProtocol"
0x180032cf6  mov     rcx, rdi; this
0x180032cf9  call    ?SetProtocol@CNfsWmiV2ServerConfig@@AEAAJPEAGK@Z; CNfsWmiV2ServerConfig::SetProtocol(ushort *,ulong)
0x180032cfe  test    eax, eax
0x180032d00  js      short loc_180032D56
0x180032d02  mov     r8d, ebx; unsigned int
0x180032d05  lea     rdx, aNlmprotocol; "NlmProtocol"
0x180032d0c  mov     rcx, rdi; this
0x180032d0f  call    ?SetProtocol@CNfsWmiV2ServerConfig@@AEAAJPEAGK@Z; CNfsWmiV2ServerConfig::SetProtocol(ushort *,ulong)
0x180032d14  test    eax, eax
0x180032d16  js      short loc_180032D56
0x180032d18  mov     r8d, ebx; unsigned int
0x180032d1b  lea     rdx, aNsmprotocol; "NsmProtocol"
0x180032d22  mov     rcx, rdi; this
0x180032d25  call    ?SetProtocol@CNfsWmiV2ServerConfig@@AEAAJPEAGK@Z; CNfsWmiV2ServerConfig::SetProtocol(ushort *,ulong)
0x180032d2a  test    eax, eax
0x180032d2c  js      short loc_180032D56
0x180032d2e  mov     r8d, ebx; unsigned int
0x180032d31  lea     rdx, aMapsvrprotocol; "MapsvrProtocol"
0x180032d38  mov     rcx, rdi; this
0x180032d3b  call    ?SetProtocol@CNfsWmiV2ServerConfig@@AEAAJPEAGK@Z; CNfsWmiV2ServerConfig::SetProtocol(ushort *,ulong)
0x180032d40  test    eax, eax
0x180032d42  js      short loc_180032D56
0x180032d44  mov     r8d, ebx; unsigned int
0x180032d47  lea     rdx, aPortmapprotoco; "PortmapProtocol"
0x180032d4e  mov     rcx, rdi; this
0x180032d51  call    ?SetProtocol@CNfsWmiV2ServerConfig@@AEAAJPEAGK@Z; CNfsWmiV2ServerConfig::SetProtocol(ushort *,ulong)
0x180032d56  mov     rbx, [rsp+28h+arg_0]
0x180032d5b  add     rsp, 20h
0x180032d5f  pop     rdi
0x180032d60  retn
```
