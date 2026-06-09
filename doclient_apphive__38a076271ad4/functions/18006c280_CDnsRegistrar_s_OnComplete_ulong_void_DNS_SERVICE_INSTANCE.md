# CDnsRegistrar::s_OnComplete(ulong,void *,_DNS_SERVICE_INSTANCE *)

- ea: `0x18006c280`
- end: `0x18006c40f`
- name: `?s_OnComplete@CDnsRegistrar@@CAXKPEAXPEAU_DNS_SERVICE_INSTANCE@@@Z`
- size: `399`
- prototype: `void __fastcall(char *, CDnsRegistrar *this, struct _DNS_SERVICE_INSTANCE *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008fb8`
- `0x18001eeac`
- `0x18006b9d4`
- `0x18006bacc`
- `0x18006c190`
- `0x18006c280`
- `0x1800a1ea4`
- `0x1800a1f08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006c3f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006c3f4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006c2ae`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006c2ae`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18006c3ea`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18006c3ea`
- `DNSAPI!DnsServiceFreeInstance` at `0x18006c408`

## string_xrefs

- `0x18006c301`: `CDnsRegistrar::_OnComplete`
- `0x18006c35c`: `CDnsRegistrar::_OnComplete`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CDnsRegistrar::s_OnComplete(char *a1, RTL_SRWLOCK *this, struct _DNS_SERVICE_INSTANCE *a3)
{
  int v5; // eax
  signed int v6; // esi
  int Ptr_high; // edi
  int Ptr; // eax
  const char *v9; // rax
  int v10; // edi
  const char *v11; // [rsp+28h] [rbp-40h]
  _BYTE v12[56]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v5 = 0;
  if ( (_DWORD)a1 != 9701 )
    v5 = (int)a1;
  v6 = (unsigned __int16)v5 | 0x80070000;
  if ( v5 <= 0 )
    v6 = v5;
  AcquireSRWLockExclusive(this + 1);
  Ptr_high = HIDWORD(this[20].Ptr);
  HIDWORD(this[20].Ptr) = 0;
  Ptr = (int)this[20].Ptr;
  if ( Ptr == 1 )
  {
    if ( v6 < 0 )
    {
      LODWORD(this[20].Ptr) = 0;
      LogResult(3u, "CDnsRegistrar::_OnComplete", 0x132u, v6, "DNS-SD registration failed");
      Ptr_high = 0;
    }
    else
    {
      LODWORD(this[20].Ptr) = 2;
      v9 = (const char *)&this[3];
      if ( this[6].Ptr > (PVOID)0xF )
        v9 = *(const char **)v9;
      LogMessage(4u, "CDnsRegistrar::_OnComplete", 0x127u, "DNS-SD instance registered: %s", v9);
      this[21].Ptr = (PVOID)(*(_QWORD *)std::chrono::steady_clock::now(v12) + 60000000000LL);
      CDnsRegistrar::_ScheduleRefresh((CDnsRegistrar *)this);
    }
  }
  else if ( Ptr == 3 )
  {
    LODWORD(this[20].Ptr) = 0;
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0x13E,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\core\\DnsRegistrar.cpp",
      (const char *)(unsigned int)v6,
      (int)"DNS-SD deregistration failed",
      v11);
    this[21].Ptr = 0;
  }
  if ( BYTE2(this[22].Ptr) && Ptr_high == 1 || !Ptr_high )
  {
    LODWORD(this[2].Ptr) = 1;
    WakeByAddressAll(&this[2]);
  }
  else
  {
    v10 = Ptr_high - 1;
    if ( v10 )
    {
      if ( v10 == 1 )
        CDnsRegistrar::_Deregister((CDnsRegistrar *)this);
    }
    else
    {
      CDnsRegistrar::_Register((CDnsRegistrar *)this);
    }
  }
  ReleaseSRWLockExclusive(this + 1);
  DnsServiceFreeInstance(a3);
}

```

## disassembly

```asm
0x18006c280  push    rbx
0x18006c282  push    rbp
0x18006c283  push    rsi
0x18006c284  push    rdi
0x18006c285  push    r14
0x18006c287  sub     rsp, 40h
0x18006c28b  mov     r14, r8
0x18006c28e  mov     rbx, rdx
0x18006c291  xor     eax, eax
0x18006c293  cmp     ecx, 25E5h
0x18006c299  cmovnz  eax, ecx
0x18006c29c  movzx   esi, ax
0x18006c29f  or      esi, 80070000h
0x18006c2a5  test    eax, eax
0x18006c2a7  cmovle  esi, eax
0x18006c2aa  lea     rcx, [rdx+8]; SRWLock
0x18006c2ae  call    cs:__imp_AcquireSRWLockExclusive
0x18006c2b4  mov     edi, [rbx+0A4h]
0x18006c2ba  mov     dword ptr [rbx+0A4h], 0
0x18006c2c4  mov     eax, [rbx+0A0h]
0x18006c2ca  cmp     eax, 1
0x18006c2cd  jnz     loc_18006C371
0x18006c2d3  test    esi, esi
0x18006c2d5  js      short loc_18006C33D
0x18006c2d7  mov     dword ptr [rbx+0A0h], 2
0x18006c2e1  lea     rax, [rbx+18h]
0x18006c2e5  cmp     qword ptr [rax+18h], 0Fh
0x18006c2ea  jbe     short loc_18006C2EF
0x18006c2ec  mov     rax, [rax]
0x18006c2ef  mov     [rsp+68h+var_48], rax
0x18006c2f4  lea     r9, aDnsSdInstanceR; "DNS-SD instance registered: %s"
0x18006c2fb  mov     r8d, 127h; unsigned int
0x18006c301  lea     rdx, aCdnsregistrarO; "CDnsRegistrar::_OnComplete"
0x18006c308  mov     ecx, 4; unsigned __int8
0x18006c30d  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x18006c312  lea     rcx, [rsp+68h+var_38]
0x18006c317  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x18006c31c  mov     rcx, [rax]
0x18006c31f  mov     rax, 0DF8475800h
0x18006c329  add     rcx, rax
0x18006c32c  mov     [rbx+0A8h], rcx
0x18006c333  mov     rcx, rbx; this
0x18006c336  call    ?_ScheduleRefresh@CDnsRegistrar@@AEAAXXZ; CDnsRegistrar::_ScheduleRefresh(void)
0x18006c33b  jmp     short loc_18006C3B0
0x18006c33d  mov     dword ptr [rbx+0A0h], 0
0x18006c347  lea     rax, aDnsSdRegistrat; "DNS-SD registration failed"
0x18006c34e  mov     [rsp+68h+var_48], rax; char *
0x18006c353  mov     r9d, esi; int
0x18006c356  mov     r8d, 132h; unsigned int
0x18006c35c  lea     rdx, aCdnsregistrarO; "CDnsRegistrar::_OnComplete"
0x18006c363  mov     ecx, 3; unsigned __int8
0x18006c368  call    ?LogResult@@YAXEPEBDIJ0ZZ; LogResult(uchar,char const *,uint,long,char const *,...)
0x18006c36d  xor     edi, edi
0x18006c36f  jmp     short loc_18006C3B0
0x18006c371  cmp     eax, 3
0x18006c374  jnz     short loc_18006C3B0
0x18006c376  mov     dword ptr [rbx+0A0h], 0
0x18006c380  mov     rcx, [rsp+68h]; this
0x18006c385  lea     rax, aDnsSdDeregistr; "DNS-SD deregistration failed"
0x18006c38c  mov     [rsp+68h+var_48], rax; int
0x18006c391  mov     r9d, esi; char *
0x18006c394  lea     r8, aCW1SSrcDeliver_74; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18006c39b  mov     edx, 13Eh; void *
0x18006c3a0  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18006c3a5  mov     qword ptr [rbx+0A8h], 0
0x18006c3b0  cmp     byte ptr [rbx+0B2h], 0
0x18006c3b7  jz      short loc_18006C3BE
0x18006c3b9  cmp     edi, 1
0x18006c3bc  jz      short loc_18006C3E0
0x18006c3be  test    edi, edi
0x18006c3c0  jz      short loc_18006C3E0
0x18006c3c2  sub     edi, 1
0x18006c3c5  jz      short loc_18006C3D6
0x18006c3c7  cmp     edi, 1
0x18006c3ca  jnz     short loc_18006C3F0
0x18006c3cc  mov     rcx, rbx; this
0x18006c3cf  call    ?_Deregister@CDnsRegistrar@@AEAAXXZ; CDnsRegistrar::_Deregister(void)
0x18006c3d4  jmp     short loc_18006C3F0
0x18006c3d6  mov     rcx, rbx; this
0x18006c3d9  call    ?_Register@CDnsRegistrar@@AEAAXXZ; CDnsRegistrar::_Register(void)
0x18006c3de  jmp     short loc_18006C3F0
0x18006c3e0  lea     rcx, [rbx+10h]; Address
0x18006c3e4  mov     dword ptr [rcx], 1
0x18006c3ea  call    cs:__imp_WakeByAddressAll
0x18006c3f0  lea     rcx, [rbx+8]; SRWLock
0x18006c3f4  call    cs:__imp_ReleaseSRWLockExclusive
0x18006c3fa  nop
0x18006c3fb  mov     rcx, r14
0x18006c3fe  add     rsp, 40h
0x18006c402  pop     r14
0x18006c404  pop     rdi
0x18006c405  pop     rsi
0x18006c406  pop     rbp
0x18006c407  pop     rbx
0x18006c408  jmp     cs:__imp_DnsServiceFreeInstance
```
