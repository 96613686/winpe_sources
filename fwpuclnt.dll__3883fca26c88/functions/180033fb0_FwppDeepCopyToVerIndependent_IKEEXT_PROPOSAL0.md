# FwppDeepCopyToVerIndependent_IKEEXT_PROPOSAL0

- ea: `0x180033fb0`
- end: `0x1800340a8`
- name: `FwppDeepCopyToVerIndependent_IKEEXT_PROPOSAL0`
- size: `248`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008358`

## callees

- `0x180007e38`
- `0x180011500`
- `0x1800120e0`
- `0x18003347c`
- `0x180033800`
- `0x180033fb0`
- `0x180035d48`

## string_xrefs

- `0x18003406f`: `FwppDeepCopyToVerIndependent_IKEEXT_DH_GROUP`
- `0x180034083`: `FwppDeepCopyToVerIndependent_IKEEXT_DH_GROUP`
- `0x180034046`: `FwppDeepCopyToVerIndependent_IKEEXT_PROPOSAL0`
- `0x18003409a`: `FwppDeepCopyToVerIndependent_IKEEXT_PROPOSAL0`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyToVerIndependent_IKEEXT_PROPOSAL0(__int64 a1, struct _SID_AND_ATTRIBUTES *a2)
{
  __int64 v4; // rbx
  _DWORD *v5; // rcx
  __int64 v6; // rax
  __int64 v8; // rax

  if ( !a1 || !a2 )
  {
    v6 = WfpReportSysErrorAsNtStatus(a1, "FwppDeepCopyToVerIndependent_IKEEXT_PROPOSAL0", 3223453724LL);
LABEL_10:
    v4 = v6;
    if ( !v6 )
      return v4;
    goto LABEL_11;
  }
  v4 = FwppDeepCopyToVerIndependent_IKEEXT_CIPHER_ALGORITHM0();
  if ( !v4 )
  {
    v4 = FwppDeepCopyToVerIndependent_IKEEXT_INTEGRITY_ALGORITHM0(a1 + 12, &a2->Attributes + 1);
    if ( !v4 )
    {
      v4 = FwppDeepCopyToVerIndependent_UINT32(a1 + 16, &a2[1]);
      if ( !v4 )
      {
        if ( a1 != -20 )
        {
          v5 = (_DWORD *)&a2[1].Sid + 1;
          if ( a2 != (struct _SID_AND_ATTRIBUTES *)-20LL )
          {
            *v5 = *(_DWORD *)(a1 + 20);
LABEL_9:
            v6 = FwppDeepCopyToVerIndependent_UINT32(a1 + 24, &a2[1].Attributes);
            goto LABEL_10;
          }
        }
        v8 = WfpReportSysErrorAsNtStatus(v5, "FwppDeepCopyToVerIndependent_IKEEXT_DH_GROUP", 3223453724LL);
        v4 = v8;
        if ( !v8 )
          goto LABEL_9;
        WfpReportError(v8, "FwppDeepCopyToVerIndependent_IKEEXT_DH_GROUP");
      }
    }
  }
LABEL_11:
  FeFreeGroupsCallback(a2);
  if ( v4 )
    WfpReportError(v4, "FwppDeepCopyToVerIndependent_IKEEXT_PROPOSAL0");
  return v4;
}

```

## disassembly

```asm
0x180033fb0  mov     [rsp+arg_0], rbx
0x180033fb5  mov     [rsp+arg_8], rsi
0x180033fba  push    rdi
0x180033fbb  sub     rsp, 20h
0x180033fbf  mov     rdi, rdx
0x180033fc2  mov     rsi, rcx
0x180033fc5  test    rcx, rcx
0x180033fc8  jz      loc_180034094
0x180033fce  test    rdx, rdx
0x180033fd1  jz      loc_180034094
0x180033fd7  call    FwppDeepCopyToVerIndependent_IKEEXT_CIPHER_ALGORITHM0
0x180033fdc  mov     rbx, rax
0x180033fdf  test    rax, rax
0x180033fe2  jnz     short loc_180034039
0x180033fe4  lea     rdx, [rdi+0Ch]
0x180033fe8  lea     rcx, [rsi+0Ch]
0x180033fec  call    FwppDeepCopyToVerIndependent_IKEEXT_INTEGRITY_ALGORITHM0
0x180033ff1  mov     rbx, rax
0x180033ff4  test    rax, rax
0x180033ff7  jnz     short loc_180034039
0x180033ff9  lea     rdx, [rdi+10h]
0x180033ffd  lea     rcx, [rsi+10h]
0x180034001  call    FwppDeepCopyToVerIndependent_UINT32
0x180034006  mov     rbx, rax
0x180034009  test    rax, rax
0x18003400c  jnz     short loc_180034039
0x18003400e  lea     rax, [rsi+14h]
0x180034012  test    rax, rax
0x180034015  jz      short loc_180034069
0x180034017  lea     rcx, [rdi+14h]
0x18003401b  test    rcx, rcx
0x18003401e  jz      short loc_180034069
0x180034020  mov     eax, [rax]
0x180034022  mov     [rcx], eax
0x180034024  lea     rdx, [rdi+18h]
0x180034028  lea     rcx, [rsi+18h]
0x18003402c  call    FwppDeepCopyToVerIndependent_UINT32
0x180034031  mov     rbx, rax
0x180034034  test    rax, rax
0x180034037  jz      short loc_180034055
0x180034039  mov     rcx, rdi; pSidAttrArray
0x18003403c  call    FeFreeGroupsCallback
0x180034041  test    rbx, rbx
0x180034044  jz      short loc_180034055
0x180034046  lea     rdx, aFwppdeepcopyto_50; "FwppDeepCopyToVerIndependent_IKEEXT_PRO"...
0x18003404d  mov     rcx, rbx
0x180034050  call    WfpReportError
0x180034055  mov     rsi, [rsp+28h+arg_8]
0x18003405a  mov     rax, rbx
0x18003405d  mov     rbx, [rsp+28h+arg_0]
0x180034062  add     rsp, 20h
0x180034066  pop     rdi
0x180034067  retn
0x180034069  mov     r8d, 0C022001Ch
0x18003406f  lea     rdx, aFwppdeepcopyto_105; "FwppDeepCopyToVerIndependent_IKEEXT_DH_"...
0x180034076  call    WfpReportSysErrorAsNtStatus
0x18003407b  mov     rbx, rax
0x18003407e  test    rax, rax
0x180034081  jz      short loc_180034024
0x180034083  lea     rdx, aFwppdeepcopyto_105; "FwppDeepCopyToVerIndependent_IKEEXT_DH_"...
0x18003408a  mov     rcx, rax
0x18003408d  call    WfpReportError
0x180034092  jmp     short loc_180034039
0x180034094  mov     r8d, 0C022001Ch
0x18003409a  lea     rdx, aFwppdeepcopyto_50; "FwppDeepCopyToVerIndependent_IKEEXT_PRO"...
0x1800340a1  call    WfpReportSysErrorAsNtStatus
0x1800340a6  jmp     short loc_180034031
```
