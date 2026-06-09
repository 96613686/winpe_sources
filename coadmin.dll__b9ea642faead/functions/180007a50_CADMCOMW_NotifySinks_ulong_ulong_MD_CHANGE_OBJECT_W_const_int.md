# CADMCOMW::NotifySinks(ulong,ulong,_MD_CHANGE_OBJECT_W * const,int)

- ea: `0x180007a50`
- end: `0x180007c0b`
- name: `?NotifySinks@CADMCOMW@@QEAAJKKQEAU_MD_CHANGE_OBJECT_W@@H@Z`
- size: `443`
- prototype: `__int64 __usercall@<rax>(CADMCOMW *__hidden this@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, struct _MD_CHANGE_OBJECT_W *const@<r9>, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000c1b0`
- `0x18000c270`
- `0x18000c2f0`

## callees

- `0x180003590`
- `0x180007a50`
- `0x18000d180`

## import_xrefs

- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180007acd`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180007acd`
- `IisRTL!PuDbgPrint` at `0x180007b42`
- `IisRTL!PuDbgPrint` at `0x180007b9c`
- `IisRTL!PuDbgPrint` at `0x180007bf3`
- `IisRTL!PuDbgPrint` at `0x180007b42`
- `IisRTL!PuDbgPrint` at `0x180007b9c`
- `IisRTL!PuDbgPrint` at `0x180007bf3`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180007a99`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180007a99`

## string_xrefs

- `0x180007b24`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180007b83`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180007bdb`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180007b16`: `CADMCOMW::NotifySinks`
- `0x180007b78`: `CADMCOMW::NotifySinks`
- `0x180007bcd`: `CADMCOMW::NotifySinks`
- `0x180007b8a`: `CreateNewContext failed with 0x%08x.\n`

## pseudocode

```c
__int64 __fastcall CADMCOMW::NotifySinks(
        CADMCOMW *this,
        int a2,
        unsigned int a3,
        struct _MD_CHANGE_OBJECT_W *const a4,
        int a5)
{
  int v5; // ebx
  CReaderWriterLock3 *v10; // r14
  int v11; // esi
  __int64 v12; // rdx
  __int64 *v13; // r8
  int v14; // eax
  bool v15; // zf
  const char *v16; // rax
  int NewContext; // eax
  const char *v18; // rax

  v5 = 0;
  if ( !*((_DWORD *)this + 3) && !CADMCOMW::sm_fShutdownInProgress )
  {
    if ( !a5 )
      goto LABEL_30;
    v10 = (CADMCOMW *)((char *)this + 800);
    v11 = 6;
    CReaderWriterLock3::ReadLock((CADMCOMW *)((char *)this + 800));
    v12 = 0;
    do
    {
      if ( !v11 )
        break;
      v13 = (__int64 *)*((_QWORD *)this + v12 + 6);
      while ( v13 && v11 )
      {
        v14 = 0;
        v15 = *((_DWORD *)v13 + 3) == a2;
        v13 = (__int64 *)*v13;
        if ( !v15 )
          v14 = v11;
        v11 = v14;
      }
      v12 = (unsigned int)(v12 + 1);
    }
    while ( (unsigned int)v12 < 5 );
    CReaderWriterLock3::ReadUnlock(v10);
    if ( v11 )
    {
LABEL_30:
      if ( !(unsigned int)COConnectionPoint::ListenersPresent((CADMCOMW *)((char *)this + 840)) )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
        {
          v16 = "change";
          if ( !a5 )
            v16 = "shutdown";
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
            5263,
            "CADMCOMW::NotifySinks",
            "Creating new %s notification context with %d elements.\n",
            v16,
            a3);
        }
        NewContext = CADMCOMW::CreateNewContext(this, a3, a4, a5);
        v5 = NewContext;
        if ( NewContext >= 0 )
        {
          v5 = 0;
        }
        else
        {
          if ( (g_dwDebugFlags & 3) == 0 )
            return (unsigned int)v5;
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
            5271,
            "CADMCOMW::NotifySinks",
            "CreateNewContext failed with 0x%08x.\n",
            NewContext);
        }
      }
    }
  }
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    v18 = "failed";
    if ( v5 >= 0 )
      v18 = "succeeded";
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
      5279,
      "CADMCOMW::NotifySinks",
      "%s with 0x%08x.\n",
      v18,
      v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180007a50  push    rbx
0x180007a52  push    rsi
0x180007a53  push    rdi
0x180007a54  push    r12
0x180007a56  push    r13
0x180007a58  push    r14
0x180007a5a  push    r15
0x180007a5c  sub     rsp, 40h
0x180007a60  xor     ebx, ebx
0x180007a62  mov     r13, r9
0x180007a65  mov     r15d, r8d
0x180007a68  mov     r12d, edx
0x180007a6b  mov     rdi, rcx
0x180007a6e  cmp     [rcx+0Ch], ebx
0x180007a71  jnz     loc_180007BA6
0x180007a77  cmp     cs:?sm_fShutdownInProgress@CADMCOMW@@2HA, ebx; int CADMCOMW::sm_fShutdownInProgress
0x180007a7d  jnz     loc_180007BA6
0x180007a83  cmp     [rsp+78h+arg_20], ebx
0x180007a8a  jz      short loc_180007ADB
0x180007a8c  lea     r14, [rcx+320h]
0x180007a93  mov     rcx, r14
0x180007a96  lea     esi, [rbx+6]
0x180007a99  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180007a9f  xor     edx, edx
0x180007aa1  test    esi, esi
0x180007aa3  jz      short loc_180007ACA
0x180007aa5  mov     r8, [rdi+rdx*8+30h]
0x180007aaa  jmp     short loc_180007ABE
0x180007aac  test    esi, esi
0x180007aae  jz      short loc_180007AC3
0x180007ab0  xor     eax, eax
0x180007ab2  cmp     [r8+0Ch], r12d
0x180007ab6  mov     r8, [r8]
0x180007ab9  cmovnz  eax, esi
0x180007abc  mov     esi, eax
0x180007abe  test    r8, r8
0x180007ac1  jnz     short loc_180007AAC
0x180007ac3  inc     edx
0x180007ac5  cmp     edx, 5
0x180007ac8  jb      short loc_180007AA1
0x180007aca  mov     rcx, r14
0x180007acd  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180007ad3  test    esi, esi
0x180007ad5  jz      loc_180007BA6
0x180007adb  lea     rcx, [rdi+348h]; this
0x180007ae2  call    ?ListenersPresent@COConnectionPoint@@QEAAJXZ; COConnectionPoint::ListenersPresent(void)
0x180007ae7  test    eax, eax
0x180007ae9  jnz     loc_180007BA6
0x180007aef  test    byte ptr cs:g_dwDebugFlags, 3
0x180007af6  jz      short loc_180007B48
0x180007af8  cmp     [rsp+78h+arg_20], ebx
0x180007aff  lea     rcx, aShutdown; "shutdown"
0x180007b06  mov     [rsp+78h+var_48], r15d
0x180007b0b  lea     rax, aChange; "change"
0x180007b12  cmovz   rax, rcx
0x180007b16  lea     r9, aCadmcomwNotify_0; "CADMCOMW::NotifySinks"
0x180007b1d  mov     rcx, cs:g_pDebug
0x180007b24  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x180007b2b  mov     [rsp+78h+var_50], rax
0x180007b30  mov     r8d, 148Fh
0x180007b36  lea     rax, aCreatingNewSNo; "Creating new %s notification context wi"...
0x180007b3d  mov     [rsp+78h+var_58], rax
0x180007b42  call    cs:__imp_PuDbgPrint
0x180007b48  mov     r9d, [rsp+78h+arg_20]; int
0x180007b50  mov     r8, r13; struct _MD_CHANGE_OBJECT_W *
0x180007b53  mov     edx, r15d; unsigned int
0x180007b56  mov     rcx, rdi; this
0x180007b59  call    ?CreateNewContext@CADMCOMW@@AEAAJKPEAU_MD_CHANGE_OBJECT_W@@H@Z; CADMCOMW::CreateNewContext(ulong,_MD_CHANGE_OBJECT_W *,int)
0x180007b5e  mov     ebx, eax
0x180007b60  test    eax, eax
0x180007b62  jns     short loc_180007BA4
0x180007b64  test    byte ptr cs:g_dwDebugFlags, 3
0x180007b6b  jz      loc_180007BF9
0x180007b71  mov     rcx, cs:g_pDebug
0x180007b78  lea     r9, aCadmcomwNotify_0; "CADMCOMW::NotifySinks"
0x180007b7f  mov     dword ptr [rsp+78h+var_50], eax
0x180007b83  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x180007b8a  lea     rax, aCreatenewconte; "CreateNewContext failed with 0x%08x.\n"
0x180007b91  mov     r8d, 1497h
0x180007b97  mov     [rsp+78h+var_58], rax
0x180007b9c  call    cs:__imp_PuDbgPrint
0x180007ba2  jmp     short loc_180007BA6
0x180007ba4  xor     ebx, ebx
0x180007ba6  test    byte ptr cs:g_dwDebugFlags, 3
0x180007bad  jz      short loc_180007BF9
0x180007baf  test    ebx, ebx
0x180007bb1  mov     [rsp+78h+var_48], ebx
0x180007bb5  lea     rcx, aSucceeded; "succeeded"
0x180007bbc  mov     r8d, 149Fh
0x180007bc2  lea     rax, aFailed; "failed"
0x180007bc9  cmovns  rax, rcx
0x180007bcd  lea     r9, aCadmcomwNotify_0; "CADMCOMW::NotifySinks"
0x180007bd4  mov     rcx, cs:g_pDebug
0x180007bdb  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x180007be2  mov     [rsp+78h+var_50], rax
0x180007be7  lea     rax, aSWith0x08x; "%s with 0x%08x.\n"
0x180007bee  mov     [rsp+78h+var_58], rax
0x180007bf3  call    cs:__imp_PuDbgPrint
0x180007bf9  mov     eax, ebx
0x180007bfb  add     rsp, 40h
0x180007bff  pop     r15
0x180007c01  pop     r14
0x180007c03  pop     r13
0x180007c05  pop     r12
0x180007c07  pop     rdi
0x180007c08  pop     rsi
0x180007c09  pop     rbx
0x180007c0a  retn
```
