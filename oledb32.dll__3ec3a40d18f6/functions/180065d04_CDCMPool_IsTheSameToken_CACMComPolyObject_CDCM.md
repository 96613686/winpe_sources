# CDCMPool::IsTheSameToken(CACMComPolyObject<CDCM> *)

- ea: `0x180065d04`
- end: `0x180065dea`
- name: `?IsTheSameToken@CDCMPool@@QEAA_NPEAV?$CACMComPolyObject@VCDCM@@@@@Z`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180065df0`

## callees

- `0x180011bcc`
- `0x180065390`
- `0x1800655cc`
- `0x180065d04`
- `0x180087010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180065dd1`
- `KERNEL32!CloseHandle` at `0x180065dd1`
- `ADVAPI32!EqualSid` at `0x180065da4`
- `ADVAPI32!EqualSid` at `0x180065da4`

## pseudocode

```c
bool __fastcall CDCMPool::IsTheSameToken(void *a1, __int64 a2)
{
  HANDLE v2; // rbx
  bool v3; // di
  __int64 v4; // rbx
  __int64 v5; // rdx
  int v6; // eax
  void *v7; // rbp
  PSID pSid1; // [rsp+30h] [rbp+8h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp+10h] BYREF

  pSid1 = a1;
  v2 = 0;
  v3 = 0;
  hObject = 0;
  if ( g_pfnNtCompareTokens )
  {
    v4 = *(_QWORD *)(a2 + 520);
    if ( (int)CDCMPool::GetCurrentToken((CDCMPool *)a1, &hObject) < 0 )
    {
      v2 = hObject;
    }
    else
    {
      v5 = v4;
      LODWORD(pSid1) = 0;
      v2 = hObject;
      if ( (int)((__int64 (__fastcall *)(HANDLE, __int64, PSID *))g_pfnNtCompareTokens)(hObject, v5, &pSid1) >= 0 )
        v6 = (int)pSid1;
      else
        v6 = 0;
      v3 = v6 == 1;
    }
  }
  else
  {
    v7 = *(void **)(a2 + 512);
    pSid1 = 0;
    if ( (int)CDCMPool::GetCurrentSID((CDCMPool *)a1, &pSid1) >= 0 )
      v3 = EqualSid(pSid1, v7);
    if ( pSid1 )
      operator delete(pSid1);
  }
  if ( v2 )
    CloseHandle(v2);
  return v3;
}

```

## disassembly

```asm
0x180065d04  mov     rax, rsp
0x180065d07  mov     [rax+18h], rbx
0x180065d0b  mov     [rax+20h], rbp
0x180065d0f  mov     [rax+8], rcx
0x180065d13  push    rdi
0x180065d14  sub     rsp, 20h
0x180065d18  xor     ebx, ebx
0x180065d1a  xor     dil, dil
0x180065d1d  cmp     cs:?g_pfnNtCompareTokens@@3P6AJPEAX0PEAH@ZEA, rbx; long (*g_pfnNtCompareTokens)(void *,void *,int *)
0x180065d24  mov     [rax+10h], rbx
0x180065d28  jz      short loc_180065D82
0x180065d2a  mov     rbx, [rdx+208h]
0x180065d31  lea     rdx, [rax+10h]; void **
0x180065d35  call    ?GetCurrentToken@CDCMPool@@QEAAJPEAPEAX@Z; CDCMPool::GetCurrentToken(void * *)
0x180065d3a  test    eax, eax
0x180065d3c  js      short loc_180065D7B
0x180065d3e  mov     rax, cs:?g_pfnNtCompareTokens@@3P6AJPEAX0PEAH@ZEA; long (*g_pfnNtCompareTokens)(void *,void *,int *)
0x180065d45  lea     r8, [rsp+28h+pSid1]
0x180065d4a  mov     rdx, rbx
0x180065d4d  mov     dword ptr [rsp+28h+pSid1], 0
0x180065d55  mov     rbx, [rsp+28h+hObject]
0x180065d5a  mov     rcx, rbx
0x180065d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d62  test    eax, eax
0x180065d64  jns     short loc_180065D6A
0x180065d66  xor     eax, eax
0x180065d68  jmp     short loc_180065D6E
0x180065d6a  mov     eax, dword ptr [rsp+28h+pSid1]
0x180065d6e  mov     ecx, 1; this
0x180065d73  cmp     eax, ecx
0x180065d75  setz    dil
0x180065d79  jmp     short loc_180065DC9
0x180065d7b  mov     rbx, [rsp+28h+hObject]
0x180065d80  jmp     short loc_180065DC9
0x180065d82  mov     rbp, [rdx+200h]
0x180065d89  lea     rdx, [rsp+28h+pSid1]; void **
0x180065d8e  mov     [rsp+28h+pSid1], rbx
0x180065d93  call    ?GetCurrentSID@CDCMPool@@QEAAJPEAPEAX@Z; CDCMPool::GetCurrentSID(void * *)
0x180065d98  test    eax, eax
0x180065d9a  js      short loc_180065DB8
0x180065d9c  mov     rcx, [rsp+28h+pSid1]; pSid1
0x180065da1  mov     rdx, rbp; pSid2
0x180065da4  call    cs:__imp_EqualSid
0x180065daa  movzx   edi, dil
0x180065dae  mov     ecx, 1
0x180065db3  test    eax, eax
0x180065db5  cmovnz  edi, ecx
0x180065db8  cmp     [rsp+28h+pSid1], rbx
0x180065dbd  jz      short loc_180065DC9
0x180065dbf  mov     rcx, [rsp+28h+pSid1]; void *
0x180065dc4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180065dc9  test    rbx, rbx
0x180065dcc  jz      short loc_180065DD7
0x180065dce  mov     rcx, rbx; hObject
0x180065dd1  call    cs:__imp_CloseHandle
0x180065dd7  mov     rbx, [rsp+28h+arg_10]
0x180065ddc  mov     al, dil
0x180065ddf  mov     rbp, [rsp+28h+arg_18]
0x180065de4  add     rsp, 20h
0x180065de8  pop     rdi
0x180065de9  retn
```
