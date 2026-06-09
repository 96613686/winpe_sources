# IIS_CONFIG_RECORD::Update(IIS_CONFIG_RECORD *)

- ea: `0x18000ae9c`
- end: `0x18000af58`
- name: `?Update@IIS_CONFIG_RECORD@@QEAAXPEAV1@@Z`
- size: `188`
- prototype: `void __fastcall(IIS_CONFIG_RECORD *__hidden this, struct IIS_CONFIG_RECORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x18000abfc`

## callees

- `0x180008be8`
- `0x18000ae9c`

## pseudocode

```c
void __fastcall IIS_CONFIG_RECORD::Update(IIS_CONFIG_RECORD *this, struct IIS_CONFIG_RECORD *a2)
{
  __int64 v2; // r10

  *((_QWORD *)this + 51) = *((_QWORD *)a2 + 51);
  *((_QWORD *)a2 + 51) = 0;
  v2 = *((_QWORD *)this + 51);
  if ( v2 )
    APPLICATION_MANAGER::Update(
      v2,
      (IIS_CONFIG_RECORD *)((char *)this + 312),
      *((_DWORD *)this + 92) == 0,
      *((_DWORD *)this + 93),
      *((_DWORD *)this + 94),
      *((_DWORD *)this + 95),
      *((_DWORD *)this + 96),
      *((_DWORD *)this + 97),
      *((_DWORD *)this + 98),
      *((_DWORD *)this + 99),
      *((_DWORD *)this + 100),
      *((_DWORD *)this + 101),
      *((const unsigned __int16 **)this + 35),
      *((_DWORD *)this + 76));
}

```

## disassembly

```asm
0x18000ae9c  sub     rsp, 78h
0x18000aea0  mov     rax, [rdx+198h]
0x18000aea7  mov     [rcx+198h], rax
0x18000aeae  mov     qword ptr [rdx+198h], 0
0x18000aeb9  mov     r10, [rcx+198h]
0x18000aec0  test    r10, r10
0x18000aec3  jz      loc_18000AF53
0x18000aec9  mov     eax, [rcx+130h]
0x18000aecf  lea     rdx, [rcx+138h]
0x18000aed6  mov     r9d, [rcx+174h]
0x18000aedd  xor     r8d, r8d
0x18000aee0  cmp     [rcx+170h], r8d
0x18000aee7  mov     [rsp+78h+var_10], eax
0x18000aeeb  mov     rax, [rcx+118h]
0x18000aef2  setz    r8b
0x18000aef6  mov     [rsp+78h+var_18], rax
0x18000aefb  mov     eax, [rcx+194h]
0x18000af01  mov     [rsp+78h+var_20], eax
0x18000af05  mov     eax, [rcx+190h]
0x18000af0b  mov     [rsp+78h+var_28], eax
0x18000af0f  mov     eax, [rcx+18Ch]
0x18000af15  mov     [rsp+78h+var_30], eax
0x18000af19  mov     eax, [rcx+188h]
0x18000af1f  mov     [rsp+78h+var_38], eax
0x18000af23  mov     eax, [rcx+184h]
0x18000af29  mov     [rsp+78h+var_40], eax
0x18000af2d  mov     eax, [rcx+180h]
0x18000af33  mov     [rsp+78h+var_48], eax
0x18000af37  mov     eax, [rcx+17Ch]
0x18000af3d  mov     [rsp+78h+var_50], eax
0x18000af41  mov     eax, [rcx+178h]
0x18000af47  mov     rcx, r10
0x18000af4a  mov     [rsp+78h+var_58], eax
0x18000af4e  call    ?Update@APPLICATION_MANAGER@@QEAAXPEAVMULTISZ@@HKKKKKKKHKPEBGW4FastCgiApplicationStdErrMode@@@Z; APPLICATION_MANAGER::Update(MULTISZ *,int,ulong,ulong,ulong,ulong,ulong,ulong,ulong,int,ulong,ushort const *,FastCgiApplicationStdErrMode)
0x18000af53  add     rsp, 78h
0x18000af57  retn
```
