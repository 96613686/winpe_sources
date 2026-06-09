# W3_APPLICATION::SetupNotificationContext(int,int,NOTIFICATION_CONTEXT *,IHttpTraceContext *)

- ea: `0x18000cf40`
- end: `0x18000d258`
- name: `?SetupNotificationContext@W3_APPLICATION@@QEAAJHHPEAVNOTIFICATION_CONTEXT@@PEAVIHttpTraceContext@@@Z`
- size: `792`
- prototype: `__int64 __usercall@<rax>(W3_APPLICATION *__hidden this@<rcx>, int@<edx>, int@<r8d>, struct NOTIFICATION_CONTEXT *@<r9>, struct IHttpTraceContext *)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x18000bce0`

## callees

- `0x180009030`
- `0x18000cf40`
- `0x180013850`
- `0x180017554`
- `0x180019588`
- `0x1800197b0`
- `0x18001c5f0`
- `0x18002fa9c`
- `0x180031054`
- `0x1800311ac`
- `0x180031534`

## import_xrefs

- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000cf9a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000d026`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000d1ae`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000cf9a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000d026`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000d1ae`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000cfef`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000cfef`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d106`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d106`

## pseudocode

```c
__int64 __fastcall W3_APPLICATION::SetupNotificationContext(
        W3_APPLICATION *this,
        int a2,
        int a3,
        struct NOTIFICATION_CONTEXT *a4,
        struct IHttpTraceContext *a5)
{
  int appended; // edi
  int v6; // r15d
  __int64 v11; // rax
  _DWORD *v12; // rbx
  _QWORD *Ptr; // rax
  unsigned int v15; // ecx
  _QWORD *v16; // rdi
  __int64 v17; // rax
  __int64 v18; // r13
  const unsigned __int16 *v19; // rdx
  const unsigned __int16 *v20; // rdi
  const unsigned __int16 *v21; // rax
  const struct _GUID *v22; // rdx
  struct VIRTUAL_MODULE *v23; // rax
  const unsigned __int16 *v24; // rdi
  const unsigned __int16 *Name; // rax
  const struct _GUID *v26; // rdx
  unsigned int v27; // [rsp+20h] [rbp-48h]
  _QWORD *v28; // [rsp+28h] [rbp-40h]
  __int64 v29; // [rsp+30h] [rbp-38h]
  struct VIRTUAL_MODULE *v30; // [rsp+30h] [rbp-38h]
  int v31; // [rsp+78h] [rbp+10h]

  appended = 0;
  v6 = 0;
  if ( !a2 || *((_BYTE *)this + 221) )
  {
    v11 = 376;
    if ( a3 )
      v11 = 1256;
  }
  else
  {
    v11 = 816;
  }
  v12 = (_DWORD *)((char *)this + v11);
  if ( *(_DWORD *)((char *)this + v11 + 176) )
    goto LABEL_5;
  CReaderWriterLock3::WriteLock((W3_APPLICATION *)((char *)this + 200));
  v6 = 1;
  if ( v12[44] )
    goto LABEL_5;
  if ( !a2 || *((_BYTE *)this + 221) )
  {
    if ( a3 )
    {
      if ( !*((_BYTE *)this + 219) )
      {
        appended = W3_APPLICATION::ResolveModules(this);
        if ( appended < 0 )
          goto LABEL_22;
      }
    }
  }
  Ptr = BUFFER::QueryPtr((W3_APPLICATION *)((char *)this + 240));
  v15 = *((_DWORD *)this + 58);
  v16 = Ptr;
  v28 = Ptr;
  v17 = 0;
  v27 = v15;
  while ( 1 )
  {
    v31 = v17;
    if ( (unsigned int)v17 >= v15 )
      break;
    v18 = v16[v17];
    v29 = v17;
    if ( *(_DWORD *)(v18 + 4) && a2 && !*((_BYTE *)this + 221) )
      goto LABEL_48;
    v19 = &dword_18003C134;
    if ( *(_QWORD *)(v18 + 24) )
      v19 = *(const unsigned __int16 **)(v18 + 24);
    if ( W3_SERVER::SatisfiesPrecondition(g_pW3Server, v19, a3, 0) )
    {
      if ( !*(_QWORD *)(v18 + 32) && !*((_BYTE *)this + 219) )
      {
        appended = W3_APPLICATION::ResolveModules(this);
        if ( appended < 0 )
          goto LABEL_22;
        v16 = BUFFER::QueryPtr((W3_APPLICATION *)((char *)this + 240));
        v28 = v16;
        v27 = *((_DWORD *)this + 58);
        v18 = v16[v29];
      }
      v23 = *(struct VIRTUAL_MODULE **)(v18 + 32);
      v30 = v23;
      if ( v23 )
      {
        appended = MODULE_LIST::AppendModule((MODULE_LIST *)v12, v23);
        if ( appended < 0 )
          goto LABEL_22;
        _InterlockedIncrement((volatile signed __int32 *)v30 + 3);
      }
      else
      {
        if ( !(unsigned int)WWWServerTraceProvider::CheckTracingEnabled(a5, 0, 4) )
          goto LABEL_18;
        v24 = &dword_18003C134;
        if ( *(_QWORD *)(v18 + 16) )
          v24 = *(const unsigned __int16 **)(v18 + 16);
        Name = APPLICATION_MODULE::GetName((APPLICATION_MODULE *)v18);
        IISGeneralEvents::VIRTUAL_MODULE_UNRESOLVED::RaiseEvent(a5, v26, Name, v24);
      }
    }
    else
    {
LABEL_48:
      if ( !(unsigned int)WWWServerTraceProvider::CheckTracingEnabled(a5, 0, 4) )
        goto LABEL_18;
      v20 = &dword_18003C134;
      if ( *(_QWORD *)(v18 + 24) )
        v20 = *(const unsigned __int16 **)(v18 + 24);
      v21 = APPLICATION_MODULE::GetName((APPLICATION_MODULE *)v18);
      IISGeneralEvents::MODULE_PRECONDITION_NOT_MATCH::RaiseEvent(a5, v22, v21, v20);
    }
    v16 = v28;
LABEL_18:
    v15 = v27;
    v17 = (unsigned int)(v31 + 1);
  }
  MODULE_LIST::Optimize((MODULE_LIST *)v12);
  appended = NOTIFICATION_CONTEXT::GenerateCachedModuleList((struct CACHED_MODULE_LIST *)v12);
  if ( appended >= 0 )
  {
LABEL_5:
    *((_QWORD *)a4 + 10) = v12;
    *((_QWORD *)a4 + 13) = BUFFER::QueryPtr((BUFFER *)(v12 + 32));
    *((_DWORD *)a4 + 30) = v12[45];
    *((_QWORD *)a4 + 14) = v12 + 46;
    if ( v6 )
      goto LABEL_24;
    return (unsigned int)appended;
  }
LABEL_22:
  if ( v12 )
    MODULE_LIST::FreeModules((MODULE_LIST *)v12);
LABEL_24:
  CReaderWriterLock3::WriteUnlock((W3_APPLICATION *)((char *)this + 200));
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18000cf40  mov     [rsp+arg_10], rbx
0x18000cf45  mov     [rsp+arg_18], rbp
0x18000cf4a  push    rsi
0x18000cf4b  push    rdi
0x18000cf4c  push    r12
0x18000cf4e  push    r14
0x18000cf50  push    r15
0x18000cf52  sub     rsp, 40h
0x18000cf56  xor     edi, edi
0x18000cf58  xor     r15d, r15d
0x18000cf5b  mov     rsi, r9
0x18000cf5e  mov     ebp, r8d
0x18000cf61  mov     r12d, edx
0x18000cf64  mov     r14, rcx
0x18000cf67  test    edx, edx
0x18000cf69  jnz     loc_18000D0C1
0x18000cf6f  test    ebp, ebp
0x18000cf71  mov     eax, 178h
0x18000cf76  mov     ecx, 4E8h
0x18000cf7b  cmovnz  eax, ecx
0x18000cf7e  lea     rbx, [rax+r14]
0x18000cf82  mov     [rsp+68h+arg_0], r13
0x18000cf87  cmp     [rbx+0B0h], edi
0x18000cf8d  jz      short loc_18000CFE8
0x18000cf8f  lea     rcx, [rbx+80h]
0x18000cf96  mov     [rsi+50h], rbx
0x18000cf9a  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000cfa1  nop     dword ptr [rax+rax+00h]
0x18000cfa6  mov     [rsi+68h], rax
0x18000cfaa  mov     eax, [rbx+0B4h]
0x18000cfb0  add     rbx, 0B8h
0x18000cfb7  mov     [rsi+78h], eax
0x18000cfba  mov     [rsi+70h], rbx
0x18000cfbe  test    r15d, r15d
0x18000cfc1  jnz     loc_18000D0FF
0x18000cfc7  mov     r13, [rsp+68h+arg_0]
0x18000cfcc  lea     r11, [rsp+68h+var_28]
0x18000cfd1  mov     rbx, [r11+40h]
0x18000cfd5  mov     eax, edi
0x18000cfd7  mov     rbp, [r11+48h]
0x18000cfdb  mov     rsp, r11
0x18000cfde  pop     r15
0x18000cfe0  pop     r14
0x18000cfe2  pop     r12
0x18000cfe4  pop     rdi
0x18000cfe5  pop     rsi
0x18000cfe6  retn
0x18000cfe8  lea     rcx, [r14+0C8h]
0x18000cfef  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000cff6  nop     dword ptr [rax+rax+00h]
0x18000cffb  mov     r15d, 1
0x18000d001  cmp     [rbx+0B0h], edi
0x18000d007  jnz     short loc_18000CF8F
0x18000d009  test    r12d, r12d
0x18000d00c  jz      loc_18000D117
0x18000d012  cmp     [r14+0DDh], dil
0x18000d019  jnz     loc_18000D117
0x18000d01f  lea     rcx, [r14+0F0h]
0x18000d026  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000d02d  nop     dword ptr [rax+rax+00h]
0x18000d032  mov     ecx, [r14+0E8h]
0x18000d039  mov     rdi, rax
0x18000d03c  mov     [rsp+68h+var_40], rax
0x18000d041  xor     eax, eax
0x18000d043  mov     [rsp+68h+var_48], ecx
0x18000d047  mov     [rsp+68h+arg_8], eax
0x18000d04b  cmp     eax, ecx
0x18000d04d  jnb     loc_18000D0D8
0x18000d053  mov     r13, [rdi+rax*8]
0x18000d057  mov     [rsp+68h+var_38], rax
0x18000d05c  cmp     dword ptr [r13+4], 0
0x18000d061  jz      short loc_18000D06C
0x18000d063  test    r12d, r12d
0x18000d066  jnz     loc_18000D13F
0x18000d06c  mov     rax, [r13+18h]
0x18000d070  lea     rdx, dword_18003C134
0x18000d077  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; this
0x18000d07e  test    rax, rax
0x18000d081  mov     r8d, ebp; int
0x18000d084  cmovnz  rdx, rax; unsigned __int16 *
0x18000d088  xor     r9d, r9d; int *
0x18000d08b  call    ?SatisfiesPrecondition@W3_SERVER@@QEBAHPEBGHPEAH@Z; W3_SERVER::SatisfiesPrecondition(ushort const *,int,int *)
0x18000d090  test    eax, eax
0x18000d092  jnz     loc_18000D184
0x18000d098  mov     rcx, [rsp+68h+arg_20]
0x18000d0a0  xor     edx, edx
0x18000d0a2  mov     r8d, 4
0x18000d0a8  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x18000d0ad  test    eax, eax
0x18000d0af  jnz     loc_18000D152
0x18000d0b5  mov     eax, [rsp+68h+arg_8]
0x18000d0b9  mov     ecx, [rsp+68h+var_48]
0x18000d0bd  inc     eax
0x18000d0bf  jmp     short loc_18000D047
0x18000d0c1  cmp     [rcx+0DDh], dil
0x18000d0c8  jnz     loc_18000CF6F
0x18000d0ce  mov     eax, 330h
0x18000d0d3  jmp     loc_18000CF7E
0x18000d0d8  mov     rcx, rbx; this
0x18000d0db  call    ?Optimize@MODULE_LIST@@QEAAXXZ; MODULE_LIST::Optimize(void)
0x18000d0e0  mov     rcx, rbx; struct CACHED_MODULE_LIST *
0x18000d0e3  call    ?GenerateCachedModuleList@NOTIFICATION_CONTEXT@@SAJPEAUCACHED_MODULE_LIST@@@Z; NOTIFICATION_CONTEXT::GenerateCachedModuleList(CACHED_MODULE_LIST *)
0x18000d0e8  mov     edi, eax
0x18000d0ea  test    eax, eax
0x18000d0ec  jns     loc_18000CF8F
0x18000d0f2  test    rbx, rbx
0x18000d0f5  jz      short loc_18000D0FF
0x18000d0f7  mov     rcx, rbx; this
0x18000d0fa  call    ?FreeModules@MODULE_LIST@@QEAAXXZ; MODULE_LIST::FreeModules(void)
0x18000d0ff  lea     rcx, [r14+0C8h]
0x18000d106  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000d10d  nop     dword ptr [rax+rax+00h]
0x18000d112  jmp     loc_18000CFC7
0x18000d117  test    ebp, ebp
0x18000d119  jz      loc_18000D01F
0x18000d11f  cmp     [r14+0DBh], dil
0x18000d126  jnz     loc_18000D01F
0x18000d12c  mov     rcx, r14; this
0x18000d12f  call    ?ResolveModules@W3_APPLICATION@@QEAAJXZ; W3_APPLICATION::ResolveModules(void)
0x18000d134  mov     edi, eax
0x18000d136  test    eax, eax
0x18000d138  js      short loc_18000D0F2
0x18000d13a  jmp     loc_18000D01F
0x18000d13f  cmp     byte ptr [r14+0DDh], 0
0x18000d147  jz      loc_18000D098
0x18000d14d  jmp     loc_18000D06C
0x18000d152  mov     rax, [r13+18h]
0x18000d156  lea     rdi, dword_18003C134
0x18000d15d  test    rax, rax
0x18000d160  mov     rcx, r13; this
0x18000d163  cmovnz  rdi, rax
0x18000d167  call    ?GetName@APPLICATION_MODULE@@QEBAPEBGXZ; APPLICATION_MODULE::GetName(void)
0x18000d16c  mov     rcx, [rsp+68h+arg_20]; struct IHttpTraceContext *
0x18000d174  mov     r9, rdi; unsigned __int16 *
0x18000d177  mov     r8, rax; unsigned __int16 *
0x18000d17a  call    ?RaiseEvent@MODULE_PRECONDITION_NOT_MATCH@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBG2@Z; IISGeneralEvents::MODULE_PRECONDITION_NOT_MATCH::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *,ushort const *)
0x18000d17f  jmp     loc_18000D24E
0x18000d184  cmp     qword ptr [r13+20h], 0
0x18000d189  jnz     short loc_18000D1D6
0x18000d18b  cmp     byte ptr [r14+0DBh], 0
0x18000d193  jnz     short loc_18000D1D6
0x18000d195  mov     rcx, r14; this
0x18000d198  call    ?ResolveModules@W3_APPLICATION@@QEAAJXZ; W3_APPLICATION::ResolveModules(void)
0x18000d19d  mov     edi, eax
0x18000d19f  test    eax, eax
0x18000d1a1  js      loc_18000D0F2
0x18000d1a7  lea     rcx, [r14+0F0h]
0x18000d1ae  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000d1b5  nop     dword ptr [rax+rax+00h]
0x18000d1ba  mov     r13, [rsp+68h+var_38]
0x18000d1bf  mov     rdi, rax
0x18000d1c2  mov     [rsp+68h+var_40], rax
0x18000d1c7  mov     eax, [r14+0E8h]
0x18000d1ce  mov     [rsp+68h+var_48], eax
0x18000d1d2  mov     r13, [rdi+r13*8]
0x18000d1d6  mov     rax, [r13+20h]
0x18000d1da  mov     [rsp+68h+var_38], rax
0x18000d1df  test    rax, rax
0x18000d1e2  jnz     short loc_18000D230
0x18000d1e4  mov     rcx, [rsp+68h+arg_20]
0x18000d1ec  xor     edx, edx
0x18000d1ee  mov     r8d, 4
0x18000d1f4  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x18000d1f9  test    eax, eax
0x18000d1fb  jz      loc_18000D0B5
0x18000d201  mov     rax, [r13+10h]
0x18000d205  lea     rdi, dword_18003C134
0x18000d20c  test    rax, rax
0x18000d20f  mov     rcx, r13; this
0x18000d212  cmovnz  rdi, rax
0x18000d216  call    ?GetName@APPLICATION_MODULE@@QEBAPEBGXZ; APPLICATION_MODULE::GetName(void)
0x18000d21b  mov     rcx, [rsp+68h+arg_20]; struct IHttpTraceContext *
0x18000d223  mov     r9, rdi; unsigned __int16 *
0x18000d226  mov     r8, rax; unsigned __int16 *
0x18000d229  call    ?RaiseEvent@VIRTUAL_MODULE_UNRESOLVED@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBG2@Z; IISGeneralEvents::VIRTUAL_MODULE_UNRESOLVED::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *,ushort const *)
0x18000d22e  jmp     short loc_18000D24E
0x18000d230  mov     rdx, rax; struct VIRTUAL_MODULE *
0x18000d233  mov     rcx, rbx; this
0x18000d236  call    ?AppendModule@MODULE_LIST@@QEAAJPEAVVIRTUAL_MODULE@@@Z; MODULE_LIST::AppendModule(VIRTUAL_MODULE *)
0x18000d23b  mov     edi, eax
0x18000d23d  test    eax, eax
0x18000d23f  js      loc_18000D0F2
0x18000d245  mov     rax, [rsp+68h+var_38]
0x18000d24a  lock inc dword ptr [rax+0Ch]
0x18000d24e  mov     rdi, [rsp+68h+var_40]
0x18000d253  jmp     loc_18000D0B5
```
