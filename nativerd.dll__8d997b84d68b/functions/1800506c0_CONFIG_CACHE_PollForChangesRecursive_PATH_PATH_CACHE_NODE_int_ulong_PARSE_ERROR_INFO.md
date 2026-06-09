# CONFIG_CACHE::PollForChangesRecursive(PATH *,_PATH_CACHE_NODE *,int *,ulong,PARSE_ERROR_INFO *)

- ea: `0x1800506c0`
- end: `0x1800507f6`
- name: `?PollForChangesRecursive@CONFIG_CACHE@@AEAAJPEAVPATH@@PEAU_PATH_CACHE_NODE@@PEAHKPEAVPARSE_ERROR_INFO@@@Z`
- size: `310`
- prototype: `__int64 __fastcall(CONFIG_CACHE *__hidden this, struct PATH *, struct _PATH_CACHE_NODE *, int *, unsigned int, struct PARSE_ERROR_INFO *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180050654`
- `0x1800506c0`

## callees

- `0x1800155a0`
- `0x180015ee0`
- `0x18004f1a0`
- `0x1800506c0`
- `0x1800507fc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800507ce`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800507ce`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800507b4`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800507b4`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180050797`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180050797`

## pseudocode

```c
__int64 __fastcall CONFIG_CACHE::PollForChangesRecursive(
        CONFIG_CACHE *this,
        struct PATH *a2,
        struct _PATH_CACHE_NODE *a3,
        int *a4,
        unsigned int a5,
        struct PARSE_ERROR_INFO *a6)
{
  struct PARSE_ERROR_INFO *v6; // r12
  int NodeChanged; // edi
  unsigned int v8; // ebp
  struct _PATH_CACHE_NODE *v10; // r8
  unsigned int v15; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int16 *v16; // [rsp+38h] [rbp-30h] BYREF
  unsigned __int64 v17; // [rsp+80h] [rbp+18h] BYREF

  v6 = a6;
  NodeChanged = 0;
  v8 = a5;
  v10 = (struct _PATH_CACHE_NODE *)*((_QWORD *)a3 + 1);
  LODWORD(v17) = 0;
  v16 = 0;
  v15 = 0;
  if ( !v10 || (NodeChanged = CONFIG_CACHE::PollForChangesRecursive(this, a2, v10, a4, a5, a6), NodeChanged >= 0) )
  {
    if ( !*a4 && v8 - *((_DWORD *)a3 + 18) > *((_DWORD *)this + 203) )
    {
      NodeChanged = CONFIG_CACHE::GetNodeChanged(this, a2, a3, (int *)&v17, v6);
      if ( NodeChanged >= 0 )
      {
        if ( (_DWORD)v17 )
        {
          NodeChanged = PATH::GetPathString(a2, *((_DWORD *)a3 + 20), (const unsigned __int16 **)&v16, &v15, &v17);
          if ( NodeChanged >= 0 )
          {
            CReaderWriterLock3::ReadUnlock((CONFIG_CACHE *)((char *)this + 344));
            NodeChanged = CONFIG_CACHE::PurgePath(this, v16, v15);
            CReaderWriterLock3::ReadLock((CONFIG_CACHE *)((char *)this + 344));
            PATH::RevertString(a2);
            if ( NodeChanged >= 0 )
              *a4 = 1;
          }
        }
        else
        {
          *((_DWORD *)a3 + 18) = GetTickCount();
          *a4 = 0;
        }
      }
    }
  }
  return (unsigned int)NodeChanged;
}

```

## disassembly

```asm
0x1800506c0  mov     rax, rsp
0x1800506c3  mov     [rax+8], rbx
0x1800506c7  mov     [rax+10h], rbp
0x1800506cb  push    rsi
0x1800506cc  push    rdi
0x1800506cd  push    r12
0x1800506cf  push    r14
0x1800506d1  push    r15
0x1800506d3  sub     rsp, 40h
0x1800506d7  mov     r12, [rsp+68h+arg_28]
0x1800506df  xor     edi, edi
0x1800506e1  mov     ebp, [rsp+68h+arg_20]
0x1800506e8  mov     rbx, r8
0x1800506eb  mov     r8, [r8+8]; struct _PATH_CACHE_NODE *
0x1800506ef  mov     rsi, r9
0x1800506f2  mov     [rax+18h], edi
0x1800506f5  mov     r15, rdx
0x1800506f8  mov     [rax-30h], rdi
0x1800506fc  mov     r14, rcx
0x1800506ff  mov     [rax-38h], edi
0x180050702  test    r8, r8
0x180050705  jz      short loc_18005071D
0x180050707  mov     [rax-40h], r12
0x18005070b  mov     [rax-48h], ebp
0x18005070e  call    ?PollForChangesRecursive@CONFIG_CACHE@@AEAAJPEAVPATH@@PEAU_PATH_CACHE_NODE@@PEAHKPEAVPARSE_ERROR_INFO@@@Z; CONFIG_CACHE::PollForChangesRecursive(PATH *,_PATH_CACHE_NODE *,int *,ulong,PARSE_ERROR_INFO *)
0x180050713  mov     edi, eax
0x180050715  test    eax, eax
0x180050717  js      loc_1800507DD
0x18005071d  cmp     dword ptr [rsi], 0
0x180050720  jnz     loc_1800507DD
0x180050726  sub     ebp, [rbx+48h]
0x180050729  cmp     ebp, [r14+32Ch]
0x180050730  jbe     loc_1800507DD
0x180050736  lea     r9, [rsp+68h+arg_10]; int *
0x18005073e  mov     [rsp+68h+var_48], r12; struct PARSE_ERROR_INFO *
0x180050743  mov     r8, rbx; struct _PATH_CACHE_NODE *
0x180050746  mov     rdx, r15; struct PATH *
0x180050749  mov     rcx, r14; this
0x18005074c  call    ?GetNodeChanged@CONFIG_CACHE@@AEAAJPEAVPATH@@PEAU_PATH_CACHE_NODE@@PEAHPEAVPARSE_ERROR_INFO@@@Z; CONFIG_CACHE::GetNodeChanged(PATH *,_PATH_CACHE_NODE *,int *,PARSE_ERROR_INFO *)
0x180050751  mov     edi, eax
0x180050753  test    eax, eax
0x180050755  js      loc_1800507DD
0x18005075b  cmp     dword ptr [rsp+68h+arg_10], 0
0x180050763  jz      short loc_1800507CE
0x180050765  mov     edx, [rbx+50h]; unsigned int
0x180050768  lea     rax, [rsp+68h+arg_10]
0x180050770  lea     r9, [rsp+68h+var_38]; unsigned int *
0x180050775  mov     [rsp+68h+var_48], rax; unsigned __int64 *
0x18005077a  lea     r8, [rsp+68h+var_30]; unsigned __int16 **
0x18005077f  mov     rcx, r15; this
0x180050782  call    ?GetPathString@PATH@@QEAAJKPEAPEBGPEAKPEA_K@Z; PATH::GetPathString(ulong,ushort const * *,ulong *,unsigned __int64 *)
0x180050787  mov     edi, eax
0x180050789  test    eax, eax
0x18005078b  js      short loc_1800507DD
0x18005078d  lea     rbx, [r14+158h]
0x180050794  mov     rcx, rbx
0x180050797  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18005079d  mov     r8d, [rsp+68h+var_38]; unsigned int
0x1800507a2  mov     rcx, r14; this
0x1800507a5  mov     rdx, [rsp+68h+var_30]; unsigned __int16 *
0x1800507aa  call    ?PurgePath@CONFIG_CACHE@@QEAAJPEBGK@Z; CONFIG_CACHE::PurgePath(ushort const *,ulong)
0x1800507af  mov     rcx, rbx
0x1800507b2  mov     edi, eax
0x1800507b4  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x1800507ba  mov     rcx, r15; this
0x1800507bd  call    ?RevertString@PATH@@QEAAXXZ; PATH::RevertString(void)
0x1800507c2  test    edi, edi
0x1800507c4  js      short loc_1800507DD
0x1800507c6  mov     dword ptr [rsi], 1
0x1800507cc  jmp     short loc_1800507DD
0x1800507ce  call    cs:__imp_GetTickCount
0x1800507d4  mov     [rbx+48h], eax
0x1800507d7  mov     dword ptr [rsi], 0
0x1800507dd  mov     rbx, [rsp+68h+arg_0]
0x1800507e2  mov     eax, edi
0x1800507e4  mov     rbp, [rsp+68h+arg_8]
0x1800507e9  add     rsp, 40h
0x1800507ed  pop     r15
0x1800507ef  pop     r14
0x1800507f1  pop     r12
0x1800507f3  pop     rdi
0x1800507f4  pop     rsi
0x1800507f5  retn
```
