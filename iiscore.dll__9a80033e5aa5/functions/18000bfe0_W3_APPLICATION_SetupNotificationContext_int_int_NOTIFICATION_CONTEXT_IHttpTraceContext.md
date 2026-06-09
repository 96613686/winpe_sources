# W3_APPLICATION::SetupNotificationContext(int,int,NOTIFICATION_CONTEXT *,IHttpTraceContext *)

- ea: `0x18000bfe0`
- end: `0x18000c2d9`
- name: `?SetupNotificationContext@W3_APPLICATION@@QEAAJHHPEAVNOTIFICATION_CONTEXT@@PEAVIHttpTraceContext@@@Z`
- size: `761`
- prototype: `__int64 __usercall@<rax>(W3_APPLICATION *__hidden this@<rcx>, int@<edx>, int@<r8d>, struct NOTIFICATION_CONTEXT *@<r9>, struct IHttpTraceContext *)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x18000aed0`

## callees

- `0x180008930`
- `0x18000bfe0`
- `0x1800128b0`
- `0x180016314`
- `0x180018108`
- `0x180018310`
- `0x18001aed0`
- `0x18002d0d4`
- `0x18002e494`
- `0x18002e5e8`
- `0x18002e960`

## import_xrefs

- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000c03a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000c0b9`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000c235`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000c03a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000c0b9`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000c235`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c088`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c088`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c193`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c193`

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
    v19 = &dword_180039134;
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
        v24 = &dword_180039134;
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
      v20 = &dword_180039134;
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
0x18000bfe0  mov     [rsp+arg_10], rbx
0x18000bfe5  mov     [rsp+arg_18], rbp
0x18000bfea  push    rsi
0x18000bfeb  push    rdi
0x18000bfec  push    r12
0x18000bfee  push    r14
0x18000bff0  push    r15
0x18000bff2  sub     rsp, 40h
0x18000bff6  xor     edi, edi
0x18000bff8  xor     r15d, r15d
0x18000bffb  mov     rsi, r9
0x18000bffe  mov     ebp, r8d
0x18000c001  mov     r12d, edx
0x18000c004  mov     r14, rcx
0x18000c007  test    edx, edx
0x18000c009  jnz     loc_18000C14E
0x18000c00f  test    ebp, ebp
0x18000c011  mov     eax, 178h
0x18000c016  mov     ecx, 4E8h
0x18000c01b  cmovnz  eax, ecx
0x18000c01e  lea     rbx, [rax+r14]
0x18000c022  mov     [rsp+68h+arg_0], r13
0x18000c027  cmp     [rbx+0B0h], edi
0x18000c02d  jz      short loc_18000C081
0x18000c02f  lea     rcx, [rbx+80h]
0x18000c036  mov     [rsi+50h], rbx
0x18000c03a  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000c040  mov     [rsi+68h], rax
0x18000c044  mov     eax, [rbx+0B4h]
0x18000c04a  add     rbx, 0B8h
0x18000c051  mov     [rsi+78h], eax
0x18000c054  mov     [rsi+70h], rbx
0x18000c058  test    r15d, r15d
0x18000c05b  jnz     loc_18000C18C
0x18000c061  mov     r13, [rsp+68h+arg_0]
0x18000c066  lea     r11, [rsp+68h+var_28]
0x18000c06b  mov     rbx, [r11+40h]
0x18000c06f  mov     eax, edi
0x18000c071  mov     rbp, [r11+48h]
0x18000c075  mov     rsp, r11
0x18000c078  pop     r15
0x18000c07a  pop     r14
0x18000c07c  pop     r12
0x18000c07e  pop     rdi
0x18000c07f  pop     rsi
0x18000c080  retn
0x18000c081  lea     rcx, [r14+0C8h]
0x18000c088  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000c08e  mov     r15d, 1
0x18000c094  cmp     [rbx+0B0h], edi
0x18000c09a  jnz     short loc_18000C02F
0x18000c09c  test    r12d, r12d
0x18000c09f  jz      loc_18000C19E
0x18000c0a5  cmp     [r14+0DDh], dil
0x18000c0ac  jnz     loc_18000C19E
0x18000c0b2  lea     rcx, [r14+0F0h]
0x18000c0b9  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000c0bf  mov     ecx, [r14+0E8h]
0x18000c0c6  mov     rdi, rax
0x18000c0c9  mov     [rsp+68h+var_40], rax
0x18000c0ce  xor     eax, eax
0x18000c0d0  mov     [rsp+68h+var_48], ecx
0x18000c0d4  mov     [rsp+68h+arg_8], eax
0x18000c0d8  cmp     eax, ecx
0x18000c0da  jnb     loc_18000C165
0x18000c0e0  mov     r13, [rdi+rax*8]
0x18000c0e4  mov     [rsp+68h+var_38], rax
0x18000c0e9  cmp     dword ptr [r13+4], 0
0x18000c0ee  jz      short loc_18000C0F9
0x18000c0f0  test    r12d, r12d
0x18000c0f3  jnz     loc_18000C1C6
0x18000c0f9  mov     rax, [r13+18h]
0x18000c0fd  lea     rdx, dword_180039134
0x18000c104  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; this
0x18000c10b  test    rax, rax
0x18000c10e  mov     r8d, ebp; int
0x18000c111  cmovnz  rdx, rax; unsigned __int16 *
0x18000c115  xor     r9d, r9d; int *
0x18000c118  call    ?SatisfiesPrecondition@W3_SERVER@@QEBAHPEBGHPEAH@Z; W3_SERVER::SatisfiesPrecondition(ushort const *,int,int *)
0x18000c11d  test    eax, eax
0x18000c11f  jnz     loc_18000C20B
0x18000c125  mov     rcx, [rsp+68h+arg_20]
0x18000c12d  xor     edx, edx
0x18000c12f  mov     r8d, 4
0x18000c135  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x18000c13a  test    eax, eax
0x18000c13c  jnz     loc_18000C1D9
0x18000c142  mov     eax, [rsp+68h+arg_8]
0x18000c146  mov     ecx, [rsp+68h+var_48]
0x18000c14a  inc     eax
0x18000c14c  jmp     short loc_18000C0D4
0x18000c14e  cmp     [rcx+0DDh], dil
0x18000c155  jnz     loc_18000C00F
0x18000c15b  mov     eax, 330h
0x18000c160  jmp     loc_18000C01E
0x18000c165  mov     rcx, rbx; this
0x18000c168  call    ?Optimize@MODULE_LIST@@QEAAXXZ; MODULE_LIST::Optimize(void)
0x18000c16d  mov     rcx, rbx; struct CACHED_MODULE_LIST *
0x18000c170  call    ?GenerateCachedModuleList@NOTIFICATION_CONTEXT@@SAJPEAUCACHED_MODULE_LIST@@@Z; NOTIFICATION_CONTEXT::GenerateCachedModuleList(CACHED_MODULE_LIST *)
0x18000c175  mov     edi, eax
0x18000c177  test    eax, eax
0x18000c179  jns     loc_18000C02F
0x18000c17f  test    rbx, rbx
0x18000c182  jz      short loc_18000C18C
0x18000c184  mov     rcx, rbx; this
0x18000c187  call    ?FreeModules@MODULE_LIST@@QEAAXXZ; MODULE_LIST::FreeModules(void)
0x18000c18c  lea     rcx, [r14+0C8h]
0x18000c193  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000c199  jmp     loc_18000C061
0x18000c19e  test    ebp, ebp
0x18000c1a0  jz      loc_18000C0B2
0x18000c1a6  cmp     [r14+0DBh], dil
0x18000c1ad  jnz     loc_18000C0B2
0x18000c1b3  mov     rcx, r14; this
0x18000c1b6  call    ?ResolveModules@W3_APPLICATION@@QEAAJXZ; W3_APPLICATION::ResolveModules(void)
0x18000c1bb  mov     edi, eax
0x18000c1bd  test    eax, eax
0x18000c1bf  js      short loc_18000C17F
0x18000c1c1  jmp     loc_18000C0B2
0x18000c1c6  cmp     byte ptr [r14+0DDh], 0
0x18000c1ce  jz      loc_18000C125
0x18000c1d4  jmp     loc_18000C0F9
0x18000c1d9  mov     rax, [r13+18h]
0x18000c1dd  lea     rdi, dword_180039134
0x18000c1e4  test    rax, rax
0x18000c1e7  mov     rcx, r13; this
0x18000c1ea  cmovnz  rdi, rax
0x18000c1ee  call    ?GetName@APPLICATION_MODULE@@QEBAPEBGXZ; APPLICATION_MODULE::GetName(void)
0x18000c1f3  mov     rcx, [rsp+68h+arg_20]; struct IHttpTraceContext *
0x18000c1fb  mov     r9, rdi; unsigned __int16 *
0x18000c1fe  mov     r8, rax; unsigned __int16 *
0x18000c201  call    ?RaiseEvent@MODULE_PRECONDITION_NOT_MATCH@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBG2@Z; IISGeneralEvents::MODULE_PRECONDITION_NOT_MATCH::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *,ushort const *)
0x18000c206  jmp     loc_18000C2CF
0x18000c20b  cmp     qword ptr [r13+20h], 0
0x18000c210  jnz     short loc_18000C257
0x18000c212  cmp     byte ptr [r14+0DBh], 0
0x18000c21a  jnz     short loc_18000C257
0x18000c21c  mov     rcx, r14; this
0x18000c21f  call    ?ResolveModules@W3_APPLICATION@@QEAAJXZ; W3_APPLICATION::ResolveModules(void)
0x18000c224  mov     edi, eax
0x18000c226  test    eax, eax
0x18000c228  js      loc_18000C17F
0x18000c22e  lea     rcx, [r14+0F0h]
0x18000c235  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000c23b  mov     r13, [rsp+68h+var_38]
0x18000c240  mov     rdi, rax
0x18000c243  mov     [rsp+68h+var_40], rax
0x18000c248  mov     eax, [r14+0E8h]
0x18000c24f  mov     [rsp+68h+var_48], eax
0x18000c253  mov     r13, [rdi+r13*8]
0x18000c257  mov     rax, [r13+20h]
0x18000c25b  mov     [rsp+68h+var_38], rax
0x18000c260  test    rax, rax
0x18000c263  jnz     short loc_18000C2B1
0x18000c265  mov     rcx, [rsp+68h+arg_20]
0x18000c26d  xor     edx, edx
0x18000c26f  mov     r8d, 4
0x18000c275  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x18000c27a  test    eax, eax
0x18000c27c  jz      loc_18000C142
0x18000c282  mov     rax, [r13+10h]
0x18000c286  lea     rdi, dword_180039134
0x18000c28d  test    rax, rax
0x18000c290  mov     rcx, r13; this
0x18000c293  cmovnz  rdi, rax
0x18000c297  call    ?GetName@APPLICATION_MODULE@@QEBAPEBGXZ; APPLICATION_MODULE::GetName(void)
0x18000c29c  mov     rcx, [rsp+68h+arg_20]; struct IHttpTraceContext *
0x18000c2a4  mov     r9, rdi; unsigned __int16 *
0x18000c2a7  mov     r8, rax; unsigned __int16 *
0x18000c2aa  call    ?RaiseEvent@VIRTUAL_MODULE_UNRESOLVED@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBG2@Z; IISGeneralEvents::VIRTUAL_MODULE_UNRESOLVED::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *,ushort const *)
0x18000c2af  jmp     short loc_18000C2CF
0x18000c2b1  mov     rdx, rax; struct VIRTUAL_MODULE *
0x18000c2b4  mov     rcx, rbx; this
0x18000c2b7  call    ?AppendModule@MODULE_LIST@@QEAAJPEAVVIRTUAL_MODULE@@@Z; MODULE_LIST::AppendModule(VIRTUAL_MODULE *)
0x18000c2bc  mov     edi, eax
0x18000c2be  test    eax, eax
0x18000c2c0  js      loc_18000C17F
0x18000c2c6  mov     rax, [rsp+68h+var_38]
0x18000c2cb  lock inc dword ptr [rax+0Ch]
0x18000c2cf  mov     rdi, [rsp+68h+var_40]
0x18000c2d4  jmp     loc_18000C142
```
