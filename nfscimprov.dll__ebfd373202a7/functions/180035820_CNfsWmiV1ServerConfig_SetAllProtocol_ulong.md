# CNfsWmiV1ServerConfig::SetAllProtocol(ulong)

- ea: `0x180035820`
- end: `0x1800358db`
- name: `?SetAllProtocol@CNfsWmiV1ServerConfig@@UEAAJK@Z`
- size: `187`
- prototype: `int(CNfsWmiV1ServerConfig *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180035200`
- `0x180035820`

## string_xrefs

- `0x1800358aa`: `MapsvrProtocol`
- `0x18003584e`: `MountProtocol`
- `0x180035865`: `NfsProtocol`
- `0x1800358c1`: `NisProtocol`
- `0x18003587c`: `NlmProtocol`
- `0x180035893`: `NsmProtocol`
- `0x180035836`: `PortmapProtocol`

## pseudocode

```c
__int64 __fastcall CNfsWmiV1ServerConfig::SetAllProtocol(struct IWbemClassObject **this, unsigned int a2)
{
  __int64 result; // rax

  result = SetUInt32Property(this[1], L"PortmapProtocol", a2);
  if ( (int)result >= 0 )
  {
    result = SetUInt32Property(this[1], L"MountProtocol", a2);
    if ( (int)result >= 0 )
    {
      result = SetUInt32Property(this[1], L"NfsProtocol", a2);
      if ( (int)result >= 0 )
      {
        result = SetUInt32Property(this[1], L"NlmProtocol", a2);
        if ( (int)result >= 0 )
        {
          result = SetUInt32Property(this[1], L"NsmProtocol", a2);
          if ( (int)result >= 0 )
          {
            result = SetUInt32Property(this[1], L"MapsvrProtocol", a2);
            if ( (int)result >= 0 )
              return SetUInt32Property(this[1], L"NisProtocol", a2);
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
0x180035820  mov     [rsp+arg_0], rbx
0x180035825  push    rdi
0x180035826  sub     rsp, 20h
0x18003582a  mov     ebx, edx
0x18003582c  mov     rdi, rcx
0x18003582f  mov     rcx, [rcx+8]; struct IWbemClassObject *
0x180035833  mov     r8d, edx; unsigned int
0x180035836  lea     rdx, aPortmapprotoco; "PortmapProtocol"
0x18003583d  call    ?SetUInt32Property@@YAJPEAUIWbemClassObject@@PEBGK@Z; SetUInt32Property(IWbemClassObject *,ushort const *,ulong)
0x180035842  test    eax, eax
0x180035844  js      loc_1800358D0
0x18003584a  mov     rcx, [rdi+8]; struct IWbemClassObject *
0x18003584e  lea     rdx, aMountprotocol; "MountProtocol"
0x180035855  mov     r8d, ebx; unsigned int
0x180035858  call    ?SetUInt32Property@@YAJPEAUIWbemClassObject@@PEBGK@Z; SetUInt32Property(IWbemClassObject *,ushort const *,ulong)
0x18003585d  test    eax, eax
0x18003585f  js      short loc_1800358D0
0x180035861  mov     rcx, [rdi+8]; struct IWbemClassObject *
0x180035865  lea     rdx, aNfsprotocol; "NfsProtocol"
0x18003586c  mov     r8d, ebx; unsigned int
0x18003586f  call    ?SetUInt32Property@@YAJPEAUIWbemClassObject@@PEBGK@Z; SetUInt32Property(IWbemClassObject *,ushort const *,ulong)
0x180035874  test    eax, eax
0x180035876  js      short loc_1800358D0
0x180035878  mov     rcx, [rdi+8]; struct IWbemClassObject *
0x18003587c  lea     rdx, aNlmprotocol; "NlmProtocol"
0x180035883  mov     r8d, ebx; unsigned int
0x180035886  call    ?SetUInt32Property@@YAJPEAUIWbemClassObject@@PEBGK@Z; SetUInt32Property(IWbemClassObject *,ushort const *,ulong)
0x18003588b  test    eax, eax
0x18003588d  js      short loc_1800358D0
0x18003588f  mov     rcx, [rdi+8]; struct IWbemClassObject *
0x180035893  lea     rdx, aNsmprotocol; "NsmProtocol"
0x18003589a  mov     r8d, ebx; unsigned int
0x18003589d  call    ?SetUInt32Property@@YAJPEAUIWbemClassObject@@PEBGK@Z; SetUInt32Property(IWbemClassObject *,ushort const *,ulong)
0x1800358a2  test    eax, eax
0x1800358a4  js      short loc_1800358D0
0x1800358a6  mov     rcx, [rdi+8]; struct IWbemClassObject *
0x1800358aa  lea     rdx, aMapsvrprotocol; "MapsvrProtocol"
0x1800358b1  mov     r8d, ebx; unsigned int
0x1800358b4  call    ?SetUInt32Property@@YAJPEAUIWbemClassObject@@PEBGK@Z; SetUInt32Property(IWbemClassObject *,ushort const *,ulong)
0x1800358b9  test    eax, eax
0x1800358bb  js      short loc_1800358D0
0x1800358bd  mov     rcx, [rdi+8]; struct IWbemClassObject *
0x1800358c1  lea     rdx, aNisprotocol; "NisProtocol"
0x1800358c8  mov     r8d, ebx; unsigned int
0x1800358cb  call    ?SetUInt32Property@@YAJPEAUIWbemClassObject@@PEBGK@Z; SetUInt32Property(IWbemClassObject *,ushort const *,ulong)
0x1800358d0  mov     rbx, [rsp+28h+arg_0]
0x1800358d5  add     rsp, 20h
0x1800358d9  pop     rdi
0x1800358da  retn
```
