# DhcpDeInitNSIMediaSense

- ea: `0x180014f80`
- end: `0x180015005`
- name: `DhcpDeInitNSIMediaSense`
- size: `133`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800147e4`
- `0x180023928`

## callees

- `0x180014f80`

## import_xrefs

- `WINNSI!NsiDisconnectFromServer` at `0x180014fef`
- `WINNSI!NsiDisconnectFromServer` at `0x180014fef`
- `WINNSI!NsiRpcDeregisterChangeNotificationEx` at `0x180014fcd`
- `WINNSI!NsiRpcDeregisterChangeNotificationEx` at `0x180014fcd`

## pseudocode

```c
__int64 DhcpDeInitNSIMediaSense()
{
  __int64 result; // rax
  __int128 v1; // [rsp+20h] [rbp-38h] BYREF
  __int128 v2; // [rsp+30h] [rbp-28h]
  __int64 v3; // [rsp+40h] [rbp-18h]

  v1 = 0;
  v2 = 0;
  v3 = 0;
  if ( (unsigned __int64)(qword_1800616E8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    *((_QWORD *)&v1 + 1) = &NPI_MS_IPV4_MODULEID;
    LODWORD(v2) = 7;
    *((_QWORD *)&v2 + 1) = qword_1800616E8;
    NsiRpcDeregisterChangeNotificationEx(qword_1800616F0, &v1);
  }
  qword_1800616E8 = 0;
  result = qword_1800616F0 - 1;
  if ( (unsigned __int64)(qword_1800616F0 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    result = NsiDisconnectFromServer(qword_1800616F0);
  qword_1800616F0 = 0;
  return result;
}

```

## disassembly

```asm
0x180014f80  mov     r11, rsp
0x180014f83  sub     rsp, 58h
0x180014f87  mov     rcx, cs:qword_1800616E8
0x180014f8e  xor     eax, eax
0x180014f90  xorps   xmm0, xmm0
0x180014f93  movups  [rsp+58h+var_38], xmm0
0x180014f98  movups  [rsp+58h+var_28], xmm0
0x180014f9d  mov     [r11-18h], rax
0x180014fa1  lea     rax, [rcx-1]
0x180014fa5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180014fa9  ja      short loc_180014FD3
0x180014fab  lea     rax, NPI_MS_IPV4_MODULEID
0x180014fb2  mov     [r11-30h], rax
0x180014fb6  lea     rdx, [r11-38h]
0x180014fba  mov     dword ptr [rsp+58h+var_28], 7
0x180014fc2  mov     [r11-20h], rcx
0x180014fc6  mov     rcx, cs:qword_1800616F0
0x180014fcd  call    cs:__imp_NsiRpcDeregisterChangeNotificationEx
0x180014fd3  mov     rcx, cs:qword_1800616F0
0x180014fda  mov     cs:qword_1800616E8, 0
0x180014fe5  lea     rax, [rcx-1]
0x180014fe9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180014fed  ja      short loc_180014FF5
0x180014fef  call    cs:__imp_NsiDisconnectFromServer
0x180014ff5  mov     cs:qword_1800616F0, 0
0x180015000  add     rsp, 58h
0x180015004  retn
```
