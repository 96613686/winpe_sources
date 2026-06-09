# AssertInZamCache

- ea: `0x180030574`
- end: `0x180030739`
- name: `AssertInZamCache`
- size: `453`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800327ec`

## callees

- `0x18000ac60`
- `0x180030460`
- `0x180030574`
- `0x1800363d4`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!NtQuerySystemTime` at `0x1800305d1`
- `ntdll!NtQuerySystemTime` at `0x1800305d1`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800305e5`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800305e5`
- `ntdll!RtlReleaseResource` at `0x180030706`
- `ntdll!RtlReleaseResource` at `0x180030706`

## string_xrefs

- `0x1800306bc`: `Added %d.%d.%d.%d/%d.%d.%d.%d to ZAM cache with current time %x/%x exp %x/%x`

## pseudocode

```c
LPVOID *__fastcall AssertInZamCache(unsigned int a1, unsigned int a2, int *a3)
{
  int v6; // ebx
  LPVOID *i; // r14
  DWORD v8; // ebx
  union _LARGE_INTEGER SystemTime; // [rsp+70h] [rbp-90h] BYREF
  LONGLONG v11; // [rsp+78h] [rbp-88h]
  int v12; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v13[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  SystemTime.QuadPart = 0;
  v12 = 0;
  memset_0(v13, 0, sizeof(v13));
  NtQuerySystemTime(&SystemTime);
  v6 = 1;
  RtlAcquireResourceExclusive(&stru_18008C6E0, 1u);
  ((void (__fastcall *)(_QWORD))UpdateZamCache)((union _LARGE_INTEGER)SystemTime.QuadPart);
  for ( i = (LPVOID *)g_leZamCache; ; i = (LPVOID *)*i )
  {
    if ( i == &g_leZamCache )
    {
      i = 0;
      goto LABEL_9;
    }
    if ( a1 == *((_DWORD *)i + 4) && a2 == *((_DWORD *)i + 5) )
      break;
  }
  if ( i )
    goto LABEL_13;
LABEL_9:
  v8 = SystemTime.LowPart + 300000000;
  v11 = SystemTime.QuadPart + 300000000;
  AddToZamCache(a1, a2, SystemTime.QuadPart + 300000000);
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v12) = 0;
    FormatRRASErrorString(
      &v12,
      L"Added %d.%d.%d.%d/%d.%d.%d.%d to ZAM cache with current time %x/%x exp %x/%x",
      (unsigned __int8)a1,
      BYTE1(a1),
      BYTE2(a1),
      HIBYTE(a1),
      (unsigned __int8)a2,
      BYTE1(a2),
      BYTE2(a2),
      HIBYTE(a2),
      SystemTime.HighPart,
      SystemTime.LowPart,
      HIDWORD(v11),
      v8);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v12);
  }
  v6 = 0;
LABEL_13:
  *a3 = v6;
  RtlReleaseResource(&stru_18008C6E0);
  return i;
}

```

## disassembly

```asm
0x180030574  mov     [rsp-8+arg_18], rbx
0x180030579  push    rbp
0x18003057a  push    rsi
0x18003057b  push    rdi
0x18003057c  push    r12
0x18003057e  push    r13
0x180030580  push    r14
0x180030582  push    r15
0x180030584  lea     rbp, [rsp-790h]
0x18003058c  sub     rsp, 890h
0x180030593  mov     rax, cs:__security_cookie
0x18003059a  xor     rax, rsp
0x18003059d  mov     [rbp+7C0h+var_40], rax
0x1800305a4  mov     r13, r8
0x1800305a7  mov     qword ptr [rsp+8C0h+SystemTime], 0
0x1800305b0  mov     r12d, edx
0x1800305b3  mov     r15d, ecx
0x1800305b6  xor     eax, eax
0x1800305b8  lea     rcx, [rbp+7C0h+var_83C]; void *
0x1800305bc  xor     edx, edx; Val
0x1800305be  mov     [rbp+7C0h+var_840], eax
0x1800305c1  mov     r8d, 7FCh; Size
0x1800305c7  call    memset_0
0x1800305cc  lea     rcx, [rsp+8C0h+SystemTime]; SystemTime
0x1800305d1  call    cs:__imp_NtQuerySystemTime
0x1800305d7  mov     ebx, 1
0x1800305dc  lea     rcx, stru_18008C6E0; Resource
0x1800305e3  mov     dl, bl; Wait
0x1800305e5  call    cs:__imp_RtlAcquireResourceExclusive
0x1800305eb  mov     rcx, qword ptr [rsp+8C0h+SystemTime]
0x1800305f0  call    UpdateZamCache
0x1800305f5  mov     r14, cs:g_leZamCache
0x1800305fc  lea     rax, g_leZamCache
0x180030603  cmp     r14, rax
0x180030606  jz      short loc_180030623
0x180030608  cmp     r15d, [r14+10h]
0x18003060c  jnz     short loc_180030614
0x18003060e  cmp     r12d, [r14+14h]
0x180030612  jz      short loc_180030619
0x180030614  mov     r14, [r14]
0x180030617  jmp     short loc_1800305FC
0x180030619  test    r14, r14
0x18003061c  jz      short loc_180030626
0x18003061e  jmp     loc_1800306FB
0x180030623  xor     r14d, r14d
0x180030626  mov     rbx, qword ptr [rsp+8C0h+SystemTime]
0x18003062b  mov     edx, r12d
0x18003062e  add     rbx, 11E1A300h
0x180030635  mov     ecx, r15d
0x180030638  mov     r8, rbx
0x18003063b  mov     [rsp+8C0h+var_848], rbx
0x180030640  call    AddToZamCache
0x180030645  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18003064c  jge     loc_1800306F9
0x180030652  xor     eax, eax
0x180030654  mov     [rsp+8C0h+var_858], ebx
0x180030658  mov     word ptr [rbp+7C0h+var_840], ax
0x18003065c  mov     r10d, r15d
0x18003065f  mov     eax, r12d
0x180030662  movzx   edx, r12b
0x180030666  shr     eax, 10h
0x180030669  mov     esi, r12d
0x18003066c  movzx   edi, al
0x18003066f  mov     eax, r12d
0x180030672  shr     eax, 8
0x180030675  movzx   r11d, al
0x180030679  mov     eax, r15d
0x18003067c  shr     eax, 10h
0x18003067f  movzx   ecx, al
0x180030682  mov     eax, r15d
0x180030685  shr     eax, 8
0x180030688  movzx   r9d, al
0x18003068c  mov     eax, dword ptr [rsp+8C0h+var_848+4]
0x180030690  mov     [rsp+8C0h+var_860], eax
0x180030694  mov     eax, dword ptr [rsp+8C0h+SystemTime]
0x180030698  mov     [rsp+8C0h+var_868], eax
0x18003069c  mov     eax, dword ptr [rsp+8C0h+SystemTime+4]
0x1800306a0  mov     [rsp+8C0h+var_870], eax
0x1800306a4  shr     r10d, 18h
0x1800306a8  shr     esi, 18h
0x1800306ab  mov     [rsp+8C0h+var_878], esi
0x1800306af  mov     [rsp+8C0h+var_880], edi
0x1800306b3  mov     [rsp+8C0h+var_888], r11d
0x1800306b8  mov     [rsp+8C0h+var_890], edx
0x1800306bc  lea     rdx, aAddedDDDDDDDDT; "Added %d.%d.%d.%d/%d.%d.%d.%d to ZAM ca"...
0x1800306c3  mov     [rsp+8C0h+var_898], r10d
0x1800306c8  mov     [rsp+8C0h+var_8A0], ecx
0x1800306cc  lea     rcx, [rbp+7C0h+var_840]
0x1800306d0  movzx   r8d, r15b
0x1800306d4  call    FormatRRASErrorString
0x1800306d9  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800306e0  jge     short loc_1800306F9
0x1800306e2  lea     r8, [rbp+7C0h+var_840]
0x1800306e6  lea     rdx, RasRtrmgrTraceInfo
0x1800306ed  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800306f4  call    McTemplateU0z_EventWriteTransfer
0x1800306f9  xor     ebx, ebx
0x1800306fb  lea     rcx, stru_18008C6E0; Resource
0x180030702  mov     [r13+0], ebx
0x180030706  call    cs:__imp_RtlReleaseResource
0x18003070c  mov     rax, r14
0x18003070f  mov     rcx, [rbp+7C0h+var_40]
0x180030716  xor     rcx, rsp; StackCookie
0x180030719  call    __security_check_cookie
0x18003071e  mov     rbx, [rsp+8C0h+arg_18]
0x180030726  add     rsp, 890h
0x18003072d  pop     r15
0x18003072f  pop     r14
0x180030731  pop     r13
0x180030733  pop     r12
0x180030735  pop     rdi
0x180030736  pop     rsi
0x180030737  pop     rbp
0x180030738  retn
```
