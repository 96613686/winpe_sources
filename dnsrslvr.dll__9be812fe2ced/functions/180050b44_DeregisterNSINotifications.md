# DeregisterNSINotifications

- ea: `0x180050b44`
- end: `0x180050d40`
- name: `DeregisterNSINotifications`
- size: `508`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18004cef0`

## callees

- `0x18000b130`
- `0x180050b44`
- `0x180086700`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180050ccd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180050ccd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180050d15`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180050d15`
- `WINNSI!NsiDisconnectFromServer` at `0x180050c83`
- `WINNSI!NsiDisconnectFromServer` at `0x180050c83`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x180050b89`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x180050bb6`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x180050be3`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x180050c10`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x180050c3d`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x180050c6a`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x180050b89`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x180050bb6`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x180050be3`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x180050c10`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x180050c3d`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x180050c6a`
- `NSI!NsiFreeTable` at `0x180050cad`
- `NSI!NsiFreeTable` at `0x180050cad`

## pseudocode

```c
void DeregisterNSINotifications()
{
  void *v0; // rcx
  __int64 v1; // rax

  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 40, WPP_71228760225f354854029c0844ed0efa_Traceguids);
  if ( qword_1800AB900 )
  {
    NsiRpcDeregisterChangeNotification(qword_1800AB908, &NPI_MS_IPV6_MODULEID, 7);
    qword_1800AB900 = 0;
  }
  if ( qword_1800AB8F8 )
  {
    NsiRpcDeregisterChangeNotification(qword_1800AB908, &NPI_MS_IPV4_MODULEID, 7);
    qword_1800AB8F8 = 0;
  }
  if ( qword_1800AB8F0 )
  {
    NsiRpcDeregisterChangeNotification(qword_1800AB908, &NPI_MS_IPV6_MODULEID, 16);
    qword_1800AB8F0 = 0;
  }
  if ( qword_1800AB8E8 )
  {
    NsiRpcDeregisterChangeNotification(qword_1800AB908, &NPI_MS_IPV4_MODULEID, 16);
    qword_1800AB8E8 = 0;
  }
  if ( qword_1800AB8E0 )
  {
    NsiRpcDeregisterChangeNotification(qword_1800AB908, &NPI_MS_NDIS_MODULEID, 1);
    qword_1800AB8E0 = 0;
  }
  if ( qword_1800AB8C8 )
  {
    NsiRpcDeregisterChangeNotification(qword_1800AB908, &NPI_MS_IPV6_MODULEID, 33);
    qword_1800AB8C8 = 0;
  }
  if ( qword_1800AB908 )
  {
    NsiDisconnectFromServer();
    qword_1800AB908 = 0;
  }
  if ( g_NdisNsiInfo != 0 )
  {
    NsiFreeTable(*((_QWORD *)&g_NdisNsiInfo + 1), 0, g_NdisNsiInfo, 0);
    g_NdisNsiInfo = 0;
    qword_1800AB8B8 = 0;
  }
  AcquireSRWLockExclusive(&stru_1800AB8C0);
  while ( 1 )
  {
    v0 = qword_1800ABD40;
    if ( qword_1800ABD40 == &qword_1800ABD40 )
      break;
    if ( *((void ***)qword_1800ABD40 + 1) != &qword_1800ABD40
      || (v1 = *(_QWORD *)qword_1800ABD40, *(void **)(*(_QWORD *)qword_1800ABD40 + 8LL) != qword_1800ABD40) )
    {
      __fastfail(3u);
    }
    qword_1800ABD40 = *(void **)qword_1800ABD40;
    *(_QWORD *)(v1 + 8) = &qword_1800ABD40;
    MIDL_user_free(v0);
  }
  ReleaseSRWLockExclusive(&stru_1800AB8C0);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 41, WPP_71228760225f354854029c0844ed0efa_Traceguids);
}

```

## disassembly

```asm
0x180050b44  push    rbx
0x180050b46  sub     rsp, 20h
0x180050b4a  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180050b51  jz      short loc_180050B69
0x180050b53  mov     edx, 28h ; '('
0x180050b58  lea     r8, WPP_71228760225f354854029c0844ed0efa_Traceguids
0x180050b5f  mov     ecx, 40Bh
0x180050b64  call    WPP_SF_
0x180050b69  mov     r9, cs:qword_1800AB900
0x180050b70  xor     ebx, ebx
0x180050b72  test    r9, r9
0x180050b75  jz      short loc_180050B96
0x180050b77  mov     rcx, cs:qword_1800AB908
0x180050b7e  lea     r8d, [rbx+7]
0x180050b82  lea     rdx, NPI_MS_IPV6_MODULEID
0x180050b89  call    cs:__imp_NsiRpcDeregisterChangeNotification
0x180050b8f  mov     cs:qword_1800AB900, rbx
0x180050b96  mov     r9, cs:qword_1800AB8F8
0x180050b9d  test    r9, r9
0x180050ba0  jz      short loc_180050BC3
0x180050ba2  mov     rcx, cs:qword_1800AB908
0x180050ba9  lea     rdx, NPI_MS_IPV4_MODULEID
0x180050bb0  mov     r8d, 7
0x180050bb6  call    cs:__imp_NsiRpcDeregisterChangeNotification
0x180050bbc  mov     cs:qword_1800AB8F8, rbx
0x180050bc3  mov     r9, cs:qword_1800AB8F0
0x180050bca  test    r9, r9
0x180050bcd  jz      short loc_180050BF0
0x180050bcf  mov     rcx, cs:qword_1800AB908
0x180050bd6  lea     rdx, NPI_MS_IPV6_MODULEID
0x180050bdd  mov     r8d, 10h
0x180050be3  call    cs:__imp_NsiRpcDeregisterChangeNotification
0x180050be9  mov     cs:qword_1800AB8F0, rbx
0x180050bf0  mov     r9, cs:qword_1800AB8E8
0x180050bf7  test    r9, r9
0x180050bfa  jz      short loc_180050C1D
0x180050bfc  mov     rcx, cs:qword_1800AB908
0x180050c03  lea     rdx, NPI_MS_IPV4_MODULEID
0x180050c0a  mov     r8d, 10h
0x180050c10  call    cs:__imp_NsiRpcDeregisterChangeNotification
0x180050c16  mov     cs:qword_1800AB8E8, rbx
0x180050c1d  mov     r9, cs:qword_1800AB8E0
0x180050c24  test    r9, r9
0x180050c27  jz      short loc_180050C4A
0x180050c29  mov     rcx, cs:qword_1800AB908
0x180050c30  lea     rdx, NPI_MS_NDIS_MODULEID
0x180050c37  mov     r8d, 1
0x180050c3d  call    cs:__imp_NsiRpcDeregisterChangeNotification
0x180050c43  mov     cs:qword_1800AB8E0, rbx
0x180050c4a  mov     r9, cs:qword_1800AB8C8
0x180050c51  test    r9, r9
0x180050c54  jz      short loc_180050C77
0x180050c56  mov     rcx, cs:qword_1800AB908
0x180050c5d  lea     rdx, NPI_MS_IPV6_MODULEID
0x180050c64  mov     r8d, 21h ; '!'
0x180050c6a  call    cs:__imp_NsiRpcDeregisterChangeNotification
0x180050c70  mov     cs:qword_1800AB8C8, rbx
0x180050c77  mov     rcx, cs:qword_1800AB908
0x180050c7e  test    rcx, rcx
0x180050c81  jz      short loc_180050C90
0x180050c83  call    cs:__imp_NsiDisconnectFromServer
0x180050c89  mov     cs:qword_1800AB908, rbx
0x180050c90  mov     rcx, qword ptr cs:g_NdisNsiInfo+8
0x180050c97  mov     r8, qword ptr cs:g_NdisNsiInfo
0x180050c9e  test    rcx, rcx
0x180050ca1  jnz     short loc_180050CA8
0x180050ca3  test    r8, r8
0x180050ca6  jz      short loc_180050CC6
0x180050ca8  xor     r9d, r9d
0x180050cab  xor     edx, edx
0x180050cad  call    cs:__imp_NsiFreeTable
0x180050cb3  xorps   xmm0, xmm0
0x180050cb6  xor     eax, eax
0x180050cb8  movups  cs:g_NdisNsiInfo, xmm0
0x180050cbf  mov     cs:qword_1800AB8B8, rax
0x180050cc6  lea     rcx, stru_1800AB8C0; SRWLock
0x180050ccd  call    cs:__imp_AcquireSRWLockExclusive
0x180050cd3  lea     rbx, qword_1800ABD40
0x180050cda  mov     rcx, cs:qword_1800ABD40; void *
0x180050ce1  cmp     rcx, rbx
0x180050ce4  jz      short loc_180050D0E
0x180050ce6  cmp     [rcx+8], rbx
0x180050cea  jnz     short loc_180050D07
0x180050cec  mov     rax, [rcx]
0x180050cef  cmp     [rax+8], rcx
0x180050cf3  jnz     short loc_180050D07
0x180050cf5  mov     cs:qword_1800ABD40, rax
0x180050cfc  mov     [rax+8], rbx
0x180050d00  call    MIDL_user_free
0x180050d05  jmp     short loc_180050CDA
0x180050d07  mov     ecx, 3
0x180050d0c  int     29h; Win8: RtlFailFast(ecx)
0x180050d0e  lea     rcx, stru_1800AB8C0; SRWLock
0x180050d15  call    cs:__imp_ReleaseSRWLockExclusive
0x180050d1b  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180050d22  jz      short loc_180050D3A
0x180050d24  mov     edx, 29h ; ')'
0x180050d29  lea     r8, WPP_71228760225f354854029c0844ed0efa_Traceguids
0x180050d30  mov     ecx, 40Bh
0x180050d35  call    WPP_SF_
0x180050d3a  add     rsp, 20h
0x180050d3e  pop     rbx
0x180050d3f  retn
```
