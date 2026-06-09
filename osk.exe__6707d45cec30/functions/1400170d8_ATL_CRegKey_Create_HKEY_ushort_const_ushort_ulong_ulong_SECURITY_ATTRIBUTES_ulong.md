# ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x1400170d8`
- end: `0x140017179`
- name: `?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `161`
- prototype: `__int64 __usercall@<rax>(ATL::CRegKey *__hidden this@<rcx>, HKEY hKey@<rdx>, LPCWSTR lpSubKey@<r8>, unsigned __int16 *@<r9>, DWORD, REGSAM, HKEY, unsigned int *)`
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140017888`
- `0x14001b51c`
- `0x14001cc50`
- `0x14001cf70`
- `0x14001f060`
- `0x140020374`
- `0x140020938`
- `0x1400252a8`
- `0x140025400`

## callees

- `0x140005c90`
- `0x1400170d8`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x14001713d`
- `ADVAPI32!RegCreateKeyExW` at `0x14001713d`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Create(
        ATL::CRegKey *this,
        HKEY hKey,
        LPCWSTR lpSubKey,
        unsigned __int16 *a4,
        DWORD dwOptions,
        REGSAM samDesired,
        HKEY phkResult,
        unsigned int *a8)
{
  unsigned int v9; // edx
  DWORD lpdwDisposition; // [rsp+78h] [rbp+20h] BYREF
  int v12; // [rsp+7Ch] [rbp+24h]

  v12 = HIDWORD(a4);
  lpdwDisposition = 0;
  phkResult = 0;
  v9 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, dwOptions, samDesired, 0, &phkResult, &lpdwDisposition);
  if ( a8 )
    *a8 = lpdwDisposition;
  if ( !v9 )
  {
    v9 = ATL::CRegKey::Close(this);
    *(_QWORD *)this = phkResult;
  }
  return v9;
}

```

## disassembly

```asm
0x1400170d8  mov     rax, rsp
0x1400170db  mov     [rax+20h], r9
0x1400170df  push    rbx
0x1400170e0  sub     rsp, 50h
0x1400170e4  mov     dword ptr [rax+20h], 0
0x1400170eb  mov     r10, r8
0x1400170ee  mov     qword ptr [rax+38h], 0
0x1400170f6  lea     rax, [rax+20h]
0x1400170fa  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x1400170ff  mov     r11, rdx
0x140017102  lea     rax, [rsp+58h+arg_30]
0x14001710a  mov     rbx, rcx
0x14001710d  mov     [rsp+58h+phkResult], rax; phkResult
0x140017112  xor     r9d, r9d; lpClass
0x140017115  mov     eax, [rsp+58h+arg_28]
0x14001711c  xor     r8d, r8d; Reserved
0x14001711f  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140017128  mov     rdx, r10; lpSubKey
0x14001712b  mov     [rsp+58h+samDesired], eax; samDesired
0x14001712f  mov     rcx, r11; hKey
0x140017132  mov     eax, [rsp+58h+arg_20]
0x140017139  mov     [rsp+58h+dwOptions], eax; dwOptions
0x14001713d  call    cs:__imp_RegCreateKeyExW
0x140017143  mov     edx, eax
0x140017145  mov     rax, [rsp+58h+arg_38]
0x14001714d  test    rax, rax
0x140017150  jz      short loc_140017158
0x140017152  mov     ecx, [rsp+58h+arg_18]
0x140017156  mov     [rax], ecx
0x140017158  test    edx, edx
0x14001715a  jnz     short loc_140017171
0x14001715c  mov     rcx, rbx; this
0x14001715f  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140017164  mov     edx, eax
0x140017166  mov     rax, [rsp+58h+arg_30]
0x14001716e  mov     [rbx], rax
0x140017171  mov     eax, edx
0x140017173  add     rsp, 50h
0x140017177  pop     rbx
0x140017178  retn
```
