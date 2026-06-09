# FwServiceSidCreateInPlace

- ea: `0x180007040`
- end: `0x18000712d`
- name: `FwServiceSidCreateInPlace`
- size: `237`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task`

## callees

- `0x180006f50`
- `0x180007040`
- `0x18000ccd4`
- `0x180011030`
- `0x18001e1d0`

## import_xrefs

- `ntdll!RtlCreateServiceSid` at `0x1800070af`
- `ntdll!RtlCreateServiceSid` at `0x1800070af`

## pseudocode

```c
__int64 __fastcall FwServiceSidCreateInPlace(WCHAR *a1)
{
  HRESULT v1; // ebx
  void *v2; // r10
  USHORT v3; // ax
  unsigned int v4; // eax
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  struct _UNICODE_STRING ServiceName; // [rsp+20h] [rbp-28h] BYREF
  size_t pcchLength; // [rsp+30h] [rbp-18h] BYREF

  pcchLength = 0;
  *(_QWORD *)&ServiceName.Length = 0;
  ServiceName.Buffer = a1;
  if ( a1 )
  {
    v1 = StringLengthWorkerW(a1, 0x104u, &pcchLength);
    if ( v1 >= 0 )
    {
      v3 = 2 * pcchLength;
      LODWORD(pcchLength) = 68;
      ServiceName.Length = v3;
      ServiceName.MaximumLength = v3;
      v4 = RtlCreateServiceSid(&ServiceName, v2, (PULONG)&pcchLength);
      v1 = FwNtStatusToHResult(v4);
      if ( v1 < 0 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v6 = 28;
LABEL_11:
          WPP_SF_d(v5[2], v6, WPP_b26c8f9d1741323f65697860432a8e18_Traceguids, (unsigned int)v1);
          return (unsigned int)v1;
        }
      }
      return (unsigned int)v1;
    }
  }
  else
  {
    v1 = -2147024809;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v6 = 27;
    goto LABEL_11;
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180007040  push    rbx
0x180007042  sub     rsp, 40h
0x180007046  mov     rax, cs:__security_cookie
0x18000704d  xor     rax, rsp
0x180007050  mov     [rsp+48h+var_10], rax
0x180007055  mov     [rsp+48h+pcchLength], 0
0x18000705e  xorps   xmm0, xmm0
0x180007061  mov     r10, rdx
0x180007064  movups  xmmword ptr [rsp+48h+ServiceName.Length], xmm0
0x180007069  mov     [rsp+48h+ServiceName.Buffer], rcx
0x18000706e  test    rcx, rcx
0x180007071  jz      short loc_1800070E2
0x180007073  lea     r8, [rsp+48h+pcchLength]; pcchLength
0x180007078  mov     edx, 104h; cchMax
0x18000707d  call    StringLengthWorkerW
0x180007082  mov     ebx, eax
0x180007084  test    eax, eax
0x180007086  js      short loc_1800070E7
0x180007088  mov     rax, [rsp+48h+pcchLength]
0x18000708d  lea     r8, [rsp+48h+pcchLength]; ServiceSidLength
0x180007092  add     rax, rax
0x180007095  mov     dword ptr [rsp+48h+pcchLength], 44h ; 'D'
0x18000709d  mov     rdx, r10; ServiceSid
0x1800070a0  mov     [rsp+48h+ServiceName.Length], ax
0x1800070a5  lea     rcx, [rsp+48h+ServiceName]; ServiceName
0x1800070aa  mov     [rsp+48h+ServiceName.MaximumLength], ax
0x1800070af  call    cs:__imp_RtlCreateServiceSid
0x1800070b5  mov     ecx, eax
0x1800070b7  call    FwNtStatusToHResult
0x1800070bc  mov     ebx, eax
0x1800070be  test    eax, eax
0x1800070c0  jns     short loc_180007118
0x1800070c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800070c9  lea     rax, WPP_GLOBAL_Control
0x1800070d0  cmp     rcx, rax
0x1800070d3  jz      short loc_180007118
0x1800070d5  test    byte ptr [rcx+1Ch], 1
0x1800070d9  jz      short loc_180007118
0x1800070db  mov     edx, 1Ch
0x1800070e0  jmp     short loc_180007105
0x1800070e2  mov     ebx, 80070057h
0x1800070e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800070ee  lea     rax, WPP_GLOBAL_Control
0x1800070f5  cmp     rcx, rax
0x1800070f8  jz      short loc_180007118
0x1800070fa  test    byte ptr [rcx+1Ch], 1
0x1800070fe  jz      short loc_180007118
0x180007100  mov     edx, 1Bh
0x180007105  mov     rcx, [rcx+10h]
0x180007109  lea     r8, WPP_b26c8f9d1741323f65697860432a8e18_Traceguids
0x180007110  mov     r9d, ebx
0x180007113  call    WPP_SF_d
0x180007118  mov     eax, ebx
0x18000711a  mov     rcx, [rsp+48h+var_10]
0x18000711f  xor     rcx, rsp; StackCookie
0x180007122  call    __security_check_cookie
0x180007127  add     rsp, 40h
0x18000712b  pop     rbx
0x18000712c  retn
```
