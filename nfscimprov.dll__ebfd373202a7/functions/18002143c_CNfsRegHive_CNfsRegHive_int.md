# CNfsRegHive::CNfsRegHive(int)

- ea: `0x18002143c`
- end: `0x180021590`
- name: `??0CNfsRegHive@@QEAA@H@Z`
- size: `340`
- prototype: `CNfsRegHive *__fastcall(CNfsRegHive *__hidden this, int)`
- caller_count: `13`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180010184`
- `0x1800103cc`
- `0x1800109c0`
- `0x180010a7c`
- `0x180010d00`
- `0x180010f28`
- `0x180011874`
- `0x180011ad4`
- `0x18001209c`
- `0x18001248c`
- `0x180012690`
- `0x180026ac4`
- `0x1800272a0`

## callees

- `0x18002143c`
- `0x180029c30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800214b3`
- `KERNEL32!GetLastError` at `0x1800214e7`
- `KERNEL32!GetLastError` at `0x1800214b3`
- `KERNEL32!GetLastError` at `0x1800214e7`
- `CLUSAPI!GetClusterKey` at `0x1800214d8`
- `CLUSAPI!GetClusterKey` at `0x1800214d8`
- `CLUSAPI!OpenCluster` at `0x1800214a4`
- `CLUSAPI!OpenCluster` at `0x1800214a4`
- `CLUSAPI!ClusterRegCreateKey` at `0x180021531`
- `CLUSAPI!ClusterRegCreateKey` at `0x180021577`
- `CLUSAPI!ClusterRegCreateKey` at `0x180021531`
- `CLUSAPI!ClusterRegCreateKey` at `0x180021577`

## pseudocode

```c
CNfsRegHive *__fastcall CNfsRegHive::CNfsRegHive(CNfsRegHive *this, int a2)
{
  HKEY *phkResult; // rsi
  HKEY *v3; // rdi
  HCLUSTER v5; // rax
  HKEY ClusterKey; // rax
  DWORD dwDisposition; // [rsp+58h] [rbp+10h] BYREF

  phkResult = (HKEY *)((char *)this + 24);
  *((_DWORD *)this + 1) = a2;
  v3 = (HKEY *)((char *)this + 32);
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  dwDisposition = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 5) = 0;
  if ( (unsigned int)NfsClusterIsClusterNode(this, this) )
    *(_DWORD *)this = 0;
  if ( *(_DWORD *)this )
  {
    v5 = OpenCluster(0);
    *((_QWORD *)this + 1) = v5;
    if ( v5 || !GetLastError() )
    {
      ClusterKey = GetClusterKey(*((HCLUSTER *)this + 1), *((_DWORD *)this + 1) != 0 ? 131097 : 983103);
      *((_QWORD *)this + 2) = ClusterKey;
      if ( (ClusterKey || !GetLastError())
        && !ClusterRegCreateKey(
              *((HKEY *)this + 2),
              L"ServerForNFS",
              0,
              *((_DWORD *)this + 1) != 0 ? 131097 : 983103,
              0,
              phkResult,
              &dwDisposition) )
      {
        ClusterRegCreateKey(
          *((HKEY *)this + 2),
          L"ServerForNFS\\Parameters",
          0,
          *((_DWORD *)this + 1) != 0 ? 131097 : 983103,
          0,
          v3,
          &dwDisposition);
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x18002143c  mov     [rsp+arg_0], rbx
0x180021441  mov     [rsp+arg_10], rsi
0x180021446  push    rdi
0x180021447  sub     rsp, 40h
0x18002144b  lea     rsi, [rcx+18h]
0x18002144f  mov     [rcx+4], edx
0x180021452  lea     rdi, [rcx+20h]
0x180021456  mov     qword ptr [rsi], 0
0x18002145d  mov     rdx, rcx
0x180021460  mov     qword ptr [rdi], 0
0x180021467  mov     rbx, rcx
0x18002146a  mov     [rsp+48h+dwDisposition], 0
0x180021472  mov     qword ptr [rcx+8], 0
0x18002147a  mov     qword ptr [rcx+10h], 0
0x180021482  mov     qword ptr [rcx+28h], 0
0x18002148a  call    NfsClusterIsClusterNode
0x18002148f  test    eax, eax
0x180021491  jz      short loc_180021499
0x180021493  mov     dword ptr [rbx], 0
0x180021499  cmp     dword ptr [rbx], 0
0x18002149c  jz      loc_18002157D
0x1800214a2  xor     ecx, ecx; lpszClusterName
0x1800214a4  call    cs:__imp_OpenCluster
0x1800214aa  mov     [rbx+8], rax
0x1800214ae  test    rax, rax
0x1800214b1  jnz     short loc_1800214C1
0x1800214b3  call    cs:__imp_GetLastError
0x1800214b9  test    eax, eax
0x1800214bb  jnz     loc_18002157D
0x1800214c1  mov     eax, [rbx+4]
0x1800214c4  mov     rcx, [rbx+8]; hCluster
0x1800214c8  neg     eax
0x1800214ca  sbb     edx, edx
0x1800214cc  and     edx, 0FFF2FFDAh
0x1800214d2  add     edx, 0F003Fh; samDesired
0x1800214d8  call    cs:__imp_GetClusterKey
0x1800214de  mov     [rbx+10h], rax
0x1800214e2  test    rax, rax
0x1800214e5  jnz     short loc_1800214F5
0x1800214e7  call    cs:__imp_GetLastError
0x1800214ed  test    eax, eax
0x1800214ef  jnz     loc_18002157D
0x1800214f5  mov     eax, [rbx+4]
0x1800214f8  lea     rdx, szSubKey; "ServerForNFS"
0x1800214ff  mov     rcx, [rbx+10h]; hKey
0x180021503  neg     eax
0x180021505  lea     rax, [rsp+48h+dwDisposition]
0x18002150a  sbb     r9d, r9d
0x18002150d  mov     [rsp+48h+lpdwDisposition], rax; lpdwDisposition
0x180021512  and     r9d, 0FFF2FFDAh
0x180021519  mov     [rsp+48h+phkResult], rsi; phkResult
0x18002151e  add     r9d, 0F003Fh; samDesired
0x180021525  mov     [rsp+48h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002152e  xor     r8d, r8d; dwOptions
0x180021531  call    cs:__imp_ClusterRegCreateKey
0x180021537  test    eax, eax
0x180021539  jnz     short loc_18002157D
0x18002153b  mov     eax, [rbx+4]
0x18002153e  lea     rdx, aServerfornfsPa; "ServerForNFS\\Parameters"
0x180021545  mov     rcx, [rbx+10h]; hKey
0x180021549  neg     eax
0x18002154b  lea     rax, [rsp+48h+dwDisposition]
0x180021550  sbb     r9d, r9d
0x180021553  mov     [rsp+48h+lpdwDisposition], rax; lpdwDisposition
0x180021558  and     r9d, 0FFF2FFDAh
0x18002155f  mov     [rsp+48h+phkResult], rdi; phkResult
0x180021564  add     r9d, 0F003Fh; samDesired
0x18002156b  mov     [rsp+48h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180021574  xor     r8d, r8d; dwOptions
0x180021577  call    cs:__imp_ClusterRegCreateKey
0x18002157d  mov     rsi, [rsp+48h+arg_10]
0x180021582  mov     rax, rbx
0x180021585  mov     rbx, [rsp+48h+arg_0]
0x18002158a  add     rsp, 40h
0x18002158e  pop     rdi
0x18002158f  retn
```
