# CWSDPublisher::EndPublication(void)

- ea: `0x1800027b0`
- end: `0x180002928`
- name: `?EndPublication@CWSDPublisher@@QEAAJXZ`
- size: `376`
- prototype: `__int64 __fastcall(CWSDPublisher *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180001bf0`

## callees

- `0x180001f24`
- `0x180001f70`
- `0x1800027b0`
- `0x1800047ac`
- `0x180006010`

## import_xrefs

- `wsdapi!WSDRemoveFirewallCheck` at `0x1800028bb`
- `wsdapi!WSDRemoveFirewallCheck` at `0x1800028bb`

## pseudocode

```c
__int64 __fastcall CWSDPublisher::EndPublication(CWSDPublisher *this)
{
  __int64 v2; // rcx
  unsigned int v3; // edi
  __int64 v4; // rcx
  void *v5; // rcx
  int v6; // eax
  bool v7; // cf

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids);
  v2 = *((_QWORD *)this + 5);
  v3 = 0;
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 5) = 0;
  }
  v4 = *((_QWORD *)this + 9);
  if ( v4 )
  {
    if ( !*((_DWORD *)this + 6) )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 40LL))(v4);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids);
    }
    v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 48LL))(*((_QWORD *)this + 9));
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 16LL))(*((_QWORD *)this + 9));
    *((_QWORD *)this + 9) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 24);
  if ( v5 )
  {
    WSDRemoveFirewallCheck(v5);
    *((_QWORD *)this + 24) = 0;
  }
  v6 = 0;
  *(_QWORD *)((char *)this + 20) = 0;
  if ( v3 )
    v7 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
  else
    v7 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    LOBYTE(v6) = !v7;
    if ( v6 )
      WPP_SF_sqd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids);
  }
  return v3;
}

```

## disassembly

```asm
0x1800027b0  mov     [rsp+arg_0], rbx
0x1800027b5  mov     [rsp+arg_8], rdi
0x1800027ba  push    r14
0x1800027bc  sub     rsp, 30h
0x1800027c0  mov     rbx, rcx
0x1800027c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800027ca  lea     r14, WPP_GLOBAL_Control
0x1800027d1  cmp     rcx, r14
0x1800027d4  jz      short loc_1800027F6
0x1800027d6  cmp     byte ptr [rcx+19h], 4
0x1800027da  jb      short loc_1800027F6
0x1800027dc  mov     rcx, [rcx+10h]
0x1800027e0  lea     r8, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids
0x1800027e7  mov     edx, 17h
0x1800027ec  mov     [rsp+38h+var_18], rbx
0x1800027f1  call    WPP_SF_sq
0x1800027f6  mov     rcx, [rbx+28h]
0x1800027fa  xor     edi, edi
0x1800027fc  test    rcx, rcx
0x1800027ff  jz      short loc_180002811
0x180002801  mov     rax, [rcx]
0x180002804  mov     rax, [rax+10h]
0x180002808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000280d  mov     [rbx+28h], rdi
0x180002811  mov     rcx, [rbx+48h]
0x180002815  test    rcx, rcx
0x180002818  jz      loc_1800028AF
0x18000281e  cmp     [rbx+18h], edi
0x180002821  jnz     short loc_18000285A
0x180002823  mov     rax, [rcx]
0x180002826  mov     rax, [rax+28h]
0x18000282a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000282f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002836  cmp     rcx, r14
0x180002839  jz      short loc_18000285A
0x18000283b  cmp     byte ptr [rcx+19h], 3
0x18000283f  jb      short loc_18000285A
0x180002841  mov     rcx, [rcx+10h]
0x180002845  lea     r8, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids
0x18000284c  mov     edx, 18h
0x180002851  mov     dword ptr [rsp+38h+var_18], eax
0x180002855  call    WPP_SF_sD
0x18000285a  mov     rcx, [rbx+48h]
0x18000285e  mov     rax, [rcx]
0x180002861  mov     rax, [rax+30h]
0x180002865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000286a  mov     edi, eax
0x18000286c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002873  cmp     rcx, r14
0x180002876  jz      short loc_180002897
0x180002878  cmp     byte ptr [rcx+19h], 3
0x18000287c  jb      short loc_180002897
0x18000287e  mov     rcx, [rcx+10h]
0x180002882  lea     r8, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids
0x180002889  mov     edx, 19h
0x18000288e  mov     dword ptr [rsp+38h+var_18], eax
0x180002892  call    WPP_SF_sD
0x180002897  mov     rcx, [rbx+48h]
0x18000289b  mov     rax, [rcx]
0x18000289e  mov     rax, [rax+10h]
0x1800028a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028a7  mov     qword ptr [rbx+48h], 0
0x1800028af  mov     rcx, [rbx+0C0h]
0x1800028b6  test    rcx, rcx
0x1800028b9  jz      short loc_1800028CC
0x1800028bb  call    cs:__imp_?WSDRemoveFirewallCheck@@YAJPEAX@Z; WSDRemoveFirewallCheck(void *)
0x1800028c1  mov     qword ptr [rbx+0C0h], 0
0x1800028cc  xor     eax, eax
0x1800028ce  mov     qword ptr [rbx+14h], 0
0x1800028d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800028dd  test    edi, edi
0x1800028df  jnz     short loc_1800028E7
0x1800028e1  cmp     byte ptr [rcx+19h], 4
0x1800028e5  jmp     short loc_1800028EB
0x1800028e7  cmp     byte ptr [rcx+19h], 2
0x1800028eb  setnb   al
0x1800028ee  cmp     rcx, r14
0x1800028f1  jz      short loc_180002915
0x1800028f3  test    eax, eax
0x1800028f5  jz      short loc_180002915
0x1800028f7  mov     rcx, [rcx+10h]
0x1800028fb  lea     r8, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids
0x180002902  mov     edx, 1Ah
0x180002907  mov     [rsp+38h+var_10], edi
0x18000290b  mov     [rsp+38h+var_18], rbx
0x180002910  call    WPP_SF_sqd
0x180002915  mov     rbx, [rsp+38h+arg_0]
0x18000291a  mov     eax, edi
0x18000291c  mov     rdi, [rsp+38h+arg_8]
0x180002921  add     rsp, 30h
0x180002925  pop     r14
0x180002927  retn
```
