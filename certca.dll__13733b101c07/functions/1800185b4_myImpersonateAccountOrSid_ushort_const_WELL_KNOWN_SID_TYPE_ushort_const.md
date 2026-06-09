# myImpersonateAccountOrSid(ushort const *,WELL_KNOWN_SID_TYPE,ushort const *)

- ea: `0x1800185b4`
- end: `0x180018617`
- name: `?myImpersonateAccountOrSid@@YAJPEBGW4WELL_KNOWN_SID_TYPE@@0@Z`
- size: `99`
- prototype: `__int64 __fastcall(const unsigned __int16 *, enum WELL_KNOWN_SID_TYPE, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180032724`
- `0x1800373bc`

## callees

- `0x180008610`
- `0x18001840c`
- `0x1800185b4`
- `0x180018620`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018609`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018609`

## pseudocode

```c
__int64 __fastcall myImpersonateAccountOrSid(
        const unsigned __int16 *a1,
        enum WELL_KNOWN_SID_TYPE a2,
        const unsigned __int16 *a3)
{
  int SidFromRid; // eax
  const unsigned __int16 *v4; // rdx
  unsigned int v5; // ebx
  unsigned int v6; // edx
  HLOCAL hMem; // [rsp+40h] [rbp+18h] BYREF

  hMem = 0;
  SidFromRid = myGetSidFromRid((enum WELL_KNOWN_SID_TYPE)a1, &hMem);
  v5 = SidFromRid;
  if ( SidFromRid )
  {
    v6 = 642449818;
  }
  else
  {
    SidFromRid = myImpersonateSid(hMem, v4);
    v5 = SidFromRid;
    if ( !SidFromRid )
    {
      v5 = 0;
      goto LABEL_7;
    }
    v6 = 642646426;
  }
  CSPrintErrorLineFileData2(0, v6, SidFromRid, 0);
LABEL_7:
  LocalFree(hMem);
  return v5;
}

```

## disassembly

```asm
0x1800185b4  mov     [rsp+hMem], r8
0x1800185b9  push    rbx
0x1800185ba  sub     rsp, 20h
0x1800185be  lea     rdx, [rsp+28h+hMem]; void **
0x1800185c3  mov     [rsp+28h+hMem], 0
0x1800185cc  call    ?myGetSidFromRid@@YAJW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; myGetSidFromRid(WELL_KNOWN_SID_TYPE,void * *)
0x1800185d1  mov     ebx, eax
0x1800185d3  test    eax, eax
0x1800185d5  jz      short loc_1800185EB
0x1800185d7  mov     edx, 264B019Ah; unsigned int
0x1800185dc  mov     r8d, eax; int
0x1800185df  xor     r9d, r9d; int
0x1800185e2  xor     ecx, ecx; unsigned __int16 *
0x1800185e4  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x1800185e9  jmp     short loc_180018604
0x1800185eb  mov     rcx, [rsp+28h+hMem]; Sid
0x1800185f0  call    ?myImpersonateSid@@YAJPEAXPEBG@Z; myImpersonateSid(void *,ushort const *)
0x1800185f5  mov     ebx, eax
0x1800185f7  test    eax, eax
0x1800185f9  jz      short loc_180018602
0x1800185fb  mov     edx, 264E019Ah
0x180018600  jmp     short loc_1800185DC
0x180018602  xor     ebx, ebx
0x180018604  mov     rcx, [rsp+28h+hMem]; hMem
0x180018609  call    cs:__imp_LocalFree
0x18001860f  mov     eax, ebx
0x180018611  add     rsp, 20h
0x180018615  pop     rbx
0x180018616  retn
```
