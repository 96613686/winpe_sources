# GMSACleanup

- ea: `0x180005510`
- end: `0x1800056c0`
- name: `GMSACleanup`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000535c`

## callees

- `0x180005510`
- `0x180006280`
- `0x1800065a8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800055a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800055b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800055d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800055eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005608`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000561f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800055a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800055b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800055d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800055eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005608`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000561f`
- `ntdll!RtlDeleteResource` at `0x180005691`
- `ntdll!RtlDeleteResource` at `0x180005691`
- `ntdll!RtlFreeUnicodeString` at `0x180005644`
- `ntdll!RtlFreeUnicodeString` at `0x180005657`
- `ntdll!RtlFreeUnicodeString` at `0x180005644`
- `ntdll!RtlFreeUnicodeString` at `0x180005657`

## pseudocode

```c
void GMSACleanup()
{
  HLOCAL *v0; // rdi
  _QWORD *v1; // rbx
  __int64 v2; // rax
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rcx
  __int128 *v10; // rax

  if ( dword_18000B67C )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_70b8577d707437755865c965214ce19a_Traceguids);
    v0 = &hMem;
    while ( dword_18000B678 )
    {
      v1 = hMem;
      if ( hMem == &hMem )
        break;
      if ( *((HLOCAL **)hMem + 1) != &hMem || (v2 = *(_QWORD *)hMem, *(HLOCAL *)(*(_QWORD *)hMem + 8LL) != hMem) )
        __fastfail(3u);
      hMem = *(HLOCAL *)hMem;
      *(_QWORD *)(v2 + 8) = &hMem;
      v3 = (void *)v1[2];
      if ( v3 )
      {
        LocalFree(v3);
        v1[2] = 0;
      }
      v4 = (void *)v1[3];
      if ( v4 )
      {
        LocalFree(v4);
        v1[3] = 0;
      }
      v5 = (void *)v1[4];
      if ( v5 )
      {
        LocalFree(v5);
        v1[4] = 0;
      }
      v6 = (void *)v1[8];
      if ( v6 )
      {
        LocalFree(v6);
        v1[8] = 0;
        v1[9] = 0;
      }
      v7 = (void *)v1[10];
      if ( v7 )
      {
        LocalFree(v7);
        v1[10] = 0;
        v1[11] = 0;
      }
      LocalFree(v1);
    }
    dword_18000B678 = 0;
    RtlFreeUnicodeString(&SourceString);
    RtlFreeUnicodeString(&stru_18000B5F8);
    v8 = 16;
    do
    {
      *(_BYTE *)v0 = 0;
      v0 = (HLOCAL *)((char *)v0 + 1);
      --v8;
    }
    while ( v8 );
    v9 = 88;
    v10 = &xmmword_18000B580;
    do
    {
      *(_BYTE *)v10 = 0;
      v10 = (__int128 *)((char *)v10 + 1);
      --v9;
    }
    while ( v9 );
    RtlDeleteResource(&Resource);
    dword_18000B67C = 0;
    WppCleanupUm();
  }
}

```

## disassembly

```asm
0x180005510  mov     [rsp+arg_0], rbx
0x180005515  mov     [rsp+arg_8], rsi
0x18000551a  push    rdi
0x18000551b  sub     rsp, 20h
0x18000551f  xor     esi, esi
0x180005521  cmp     cs:dword_18000B67C, esi
0x180005527  jz      loc_1800056A8
0x18000552d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005534  lea     rax, WPP_GLOBAL_Control
0x18000553b  cmp     rcx, rax
0x18000553e  jz      short loc_180005559
0x180005540  test    byte ptr [rcx+1Ch], 8
0x180005544  jz      short loc_180005559
0x180005546  mov     rcx, [rcx+10h]
0x18000554a  lea     edx, [rsi+0Fh]
0x18000554d  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180005554  call    WPP_SF_
0x180005559  lea     rdi, hMem
0x180005560  jmp     loc_18000562B
0x180005565  mov     rbx, cs:hMem
0x18000556c  cmp     rbx, rdi
0x18000556f  jz      loc_180005637
0x180005575  cmp     [rbx+8], rdi
0x180005579  jnz     loc_1800056B9
0x18000557f  mov     rax, [rbx]
0x180005582  cmp     [rax+8], rbx
0x180005586  jnz     loc_1800056B9
0x18000558c  mov     cs:hMem, rax
0x180005593  mov     [rax+8], rdi
0x180005597  mov     rcx, [rbx+10h]; hMem
0x18000559b  test    rcx, rcx
0x18000559e  jz      short loc_1800055B0
0x1800055a0  call    cs:__imp_LocalFree
0x1800055a7  nop     dword ptr [rax+rax+00h]
0x1800055ac  mov     [rbx+10h], rsi
0x1800055b0  mov     rcx, [rbx+18h]; hMem
0x1800055b4  test    rcx, rcx
0x1800055b7  jz      short loc_1800055C9
0x1800055b9  call    cs:__imp_LocalFree
0x1800055c0  nop     dword ptr [rax+rax+00h]
0x1800055c5  mov     [rbx+18h], rsi
0x1800055c9  mov     rcx, [rbx+20h]; hMem
0x1800055cd  test    rcx, rcx
0x1800055d0  jz      short loc_1800055E2
0x1800055d2  call    cs:__imp_LocalFree
0x1800055d9  nop     dword ptr [rax+rax+00h]
0x1800055de  mov     [rbx+20h], rsi
0x1800055e2  mov     rcx, [rbx+40h]; hMem
0x1800055e6  test    rcx, rcx
0x1800055e9  jz      short loc_1800055FF
0x1800055eb  call    cs:__imp_LocalFree
0x1800055f2  nop     dword ptr [rax+rax+00h]
0x1800055f7  mov     [rbx+40h], rsi
0x1800055fb  mov     [rbx+48h], rsi
0x1800055ff  mov     rcx, [rbx+50h]; hMem
0x180005603  test    rcx, rcx
0x180005606  jz      short loc_18000561C
0x180005608  call    cs:__imp_LocalFree
0x18000560f  nop     dword ptr [rax+rax+00h]
0x180005614  mov     [rbx+50h], rsi
0x180005618  mov     [rbx+58h], rsi
0x18000561c  mov     rcx, rbx; hMem
0x18000561f  call    cs:__imp_LocalFree
0x180005626  nop     dword ptr [rax+rax+00h]
0x18000562b  cmp     cs:dword_18000B678, esi
0x180005631  jnz     loc_180005565
0x180005637  lea     rcx, SourceString; UnicodeString
0x18000563e  mov     cs:dword_18000B678, esi
0x180005644  call    cs:__imp_RtlFreeUnicodeString
0x18000564b  nop     dword ptr [rax+rax+00h]
0x180005650  lea     rcx, stru_18000B5F8; UnicodeString
0x180005657  call    cs:__imp_RtlFreeUnicodeString
0x18000565e  nop     dword ptr [rax+rax+00h]
0x180005663  mov     eax, 10h
0x180005668  mov     [rdi], sil
0x18000566b  inc     rdi
0x18000566e  sub     rax, 1
0x180005672  jnz     short loc_180005668
0x180005674  lea     ecx, [rax+58h]
0x180005677  lea     rax, xmmword_18000B580
0x18000567e  mov     [rax], sil
0x180005681  inc     rax
0x180005684  sub     rcx, 1
0x180005688  jnz     short loc_18000567E
0x18000568a  lea     rcx, Resource; Resource
0x180005691  call    cs:__imp_RtlDeleteResource
0x180005698  nop     dword ptr [rax+rax+00h]
0x18000569d  mov     cs:dword_18000B67C, esi
0x1800056a3  call    WppCleanupUm
0x1800056a8  mov     rbx, [rsp+28h+arg_0]
0x1800056ad  mov     rsi, [rsp+28h+arg_8]
0x1800056b2  add     rsp, 20h
0x1800056b6  pop     rdi
0x1800056b7  retn
0x1800056b9  mov     ecx, 3
0x1800056be  int     29h; Win8: RtlFailFast(ecx)
```
