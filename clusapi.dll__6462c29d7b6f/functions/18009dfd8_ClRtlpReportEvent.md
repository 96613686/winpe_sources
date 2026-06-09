# ClRtlpReportEvent

- ea: `0x18009dfd8`
- end: `0x18009e194`
- name: `ClRtlpReportEvent`
- size: `444`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800795d0`
- `0x18009e19c`
- `0x18009f0a8`

## callees

- `0x180002f50`
- `0x180003c14`
- `0x18009dfd8`

## import_xrefs

- `ntdll!EtwEventRegister` at `0x18009e05b`
- `ntdll!EtwEventRegister` at `0x18009e05b`
- `ntdll!EtwEventWrite` at `0x18009e162`
- `ntdll!EtwEventWrite` at `0x18009e162`
- `ntdll!EtwEventEnabled` at `0x18009e088`
- `ntdll!EtwEventEnabled` at `0x18009e088`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e068`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e068`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009e042`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009e042`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e07a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e07a`

## pseudocode

```c
DWORD __fastcall ClRtlpReportEvent(__int16 a1, __int64 a2, unsigned __int16 a3, __int64 a4, __int64 a5)
{
  __int64 v6; // rcx
  int v8; // ebp
  DWORD result; // eax
  unsigned int v10; // esi
  unsigned __int16 v11; // ax
  _BYTE *v12; // rcx
  unsigned int v13; // r8d
  unsigned int v14; // r10d
  __int64 *v15; // rdx
  __int64 v16; // rax
  int v17; // eax
  _QWORD v18[2]; // [rsp+20h] [rbp-158h] BYREF
  _BYTE v19[256]; // [rsp+30h] [rbp-148h] BYREF
  __int64 v20; // [rsp+130h] [rbp-48h] BYREF
  wchar_t v21; // [rsp+138h] [rbp-40h]

  v6 = PublisherHandle;
  v8 = a3;
  LODWORD(v18[0]) = 0;
  v20 = *(_QWORD *)L"NULL";
  v21 = aNull_0[4];
  if ( !PublisherHandle )
  {
    EnterCriticalSection(&EventLogLock);
    EtwEventRegister(MICROSOFT_FAILOVER_CLUSTER_PUBLISHER, 0, 0, &PublisherHandle, v18[0], v18[1]);
    LeaveCriticalSection(&EventLogLock);
    v6 = PublisherHandle;
    if ( !PublisherHandle )
      return GetLastError();
  }
  result = EtwEventEnabled(v6, a2);
  if ( (_BYTE)result )
  {
    if ( !*(_WORD *)(a2 + 6) )
      *(_WORD *)(a2 + 6) = a1;
    v10 = v8 + 2;
    if ( (unsigned int)(v8 + 2) > 0x10 )
      v10 = 16;
    memset_0(v19, 0, 16LL * v10);
    v11 = 14;
    v12 = v19;
    v13 = 0;
    if ( (unsigned int)(v8 + 2) <= 0x10 )
      v11 = v8;
    v14 = v11;
    if ( v11 )
    {
      do
      {
        v15 = *(__int64 **)(a5 + 8LL * v13);
        if ( v15 )
        {
          v16 = -1;
          do
            ++v16;
          while ( *((_WORD *)v15 + v16) );
          v17 = 2 * v16 + 2;
        }
        else
        {
          v17 = 10;
          v15 = &v20;
        }
        *(_QWORD *)v12 = v15;
        ++v13;
        *((_DWORD *)v12 + 2) = v17;
        *((_DWORD *)v12 + 3) = 0;
        v12 += 16;
      }
      while ( v13 < v14 );
    }
    *((_QWORD *)v12 + 1) = 4;
    *(_QWORD *)v12 = v18;
    *((_QWORD *)v12 + 2) = 0;
    *((_QWORD *)v12 + 3) = 0;
    LODWORD(v18[0]) = 0;
    return EtwEventWrite(PublisherHandle, a2, v10, v19);
  }
  return result;
}

```

## disassembly

```asm
0x18009dfd8  mov     r11, rsp
0x18009dfdb  mov     [r11+8], rbx
0x18009dfdf  mov     [r11+20h], rbp
0x18009dfe3  push    rsi
0x18009dfe4  push    rdi
0x18009dfe5  push    r12
0x18009dfe7  push    r14
0x18009dfe9  push    r15
0x18009dfeb  sub     rsp, 150h
0x18009dff2  mov     rax, cs:__security_cookie
0x18009dff9  xor     rax, rsp
0x18009dffc  mov     [rsp+178h+var_38], rax
0x18009e004  movsd   xmm0, qword ptr cs:aNull_0; "NULL"
0x18009e00c  xor     r15d, r15d
0x18009e00f  movzx   eax, word ptr cs:aNull_0+8; ""
0x18009e016  mov     ebx, ecx
0x18009e018  mov     rcx, cs:PublisherHandle
0x18009e01f  mov     rdi, rdx
0x18009e022  movzx   ebp, r8w
0x18009e026  mov     [rsp+178h+var_158], r15d
0x18009e02b  movsd   qword ptr [r11-48h], xmm0
0x18009e031  mov     [r11-40h], ax
0x18009e036  test    rcx, rcx
0x18009e039  jnz     short loc_18009E085
0x18009e03b  lea     rcx, EventLogLock; lpCriticalSection
0x18009e042  call    cs:__imp_EnterCriticalSection
0x18009e048  lea     r9, PublisherHandle
0x18009e04f  xor     r8d, r8d
0x18009e052  xor     edx, edx
0x18009e054  lea     rcx, MICROSOFT_FAILOVER_CLUSTER_PUBLISHER
0x18009e05b  call    cs:__imp_EtwEventRegister
0x18009e061  lea     rcx, EventLogLock; lpCriticalSection
0x18009e068  call    cs:__imp_LeaveCriticalSection
0x18009e06e  mov     rcx, cs:PublisherHandle
0x18009e075  test    rcx, rcx
0x18009e078  jnz     short loc_18009E085
0x18009e07a  call    cs:__imp_GetLastError
0x18009e080  jmp     loc_18009E168
0x18009e085  mov     rdx, rdi
0x18009e088  call    cs:__imp_EtwEventEnabled
0x18009e08e  test    al, al
0x18009e090  jz      loc_18009E168
0x18009e096  mov     r14, [rsp+178h+arg_20]
0x18009e09e  cmp     [rdi+6], r15w
0x18009e0a3  jnz     short loc_18009E0A9
0x18009e0a5  mov     [rdi+6], bx
0x18009e0a9  lea     ebx, [rbp+2]
0x18009e0ac  mov     r12d, 10h
0x18009e0b2  cmp     ebx, r12d
0x18009e0b5  lea     rcx, [rsp+178h+var_148]; void *
0x18009e0ba  mov     esi, ebx
0x18009e0bc  cmova   esi, r12d
0x18009e0c0  xor     edx, edx; Val
0x18009e0c2  mov     r8d, esi
0x18009e0c5  shl     r8, 4; Size
0x18009e0c9  call    memset_0
0x18009e0ce  cmp     ebx, r12d
0x18009e0d1  lea     eax, [r12-2]
0x18009e0d6  lea     rcx, [rsp+178h+var_148]
0x18009e0db  mov     r8d, r15d
0x18009e0de  cmovbe  ax, bp
0x18009e0e2  movzx   r10d, ax
0x18009e0e6  test    r10d, r10d
0x18009e0e9  jz      short loc_18009E133
0x18009e0eb  mov     eax, r8d
0x18009e0ee  mov     rdx, [r14+rax*8]
0x18009e0f2  test    rdx, rdx
0x18009e0f5  jz      short loc_18009E10E
0x18009e0f7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009e0fb  inc     rax
0x18009e0fe  cmp     [rdx+rax*2], r15w
0x18009e103  jnz     short loc_18009E0FB
0x18009e105  lea     eax, ds:2[rax*2]
0x18009e10c  jmp     short loc_18009E11B
0x18009e10e  mov     eax, 0Ah
0x18009e113  lea     rdx, [rsp+178h+var_48]
0x18009e11b  mov     [rcx], rdx
0x18009e11e  inc     r8d
0x18009e121  mov     [rcx+8], eax
0x18009e124  mov     r9d, r15d
0x18009e127  mov     [rcx+0Ch], r15d
0x18009e12b  add     rcx, r12
0x18009e12e  cmp     r8d, r10d
0x18009e131  jb      short loc_18009E0EB
0x18009e133  mov     qword ptr [rcx+8], 4
0x18009e13b  lea     rax, [rsp+178h+var_158]
0x18009e140  mov     [rcx], rax
0x18009e143  lea     r9, [rsp+178h+var_148]
0x18009e148  mov     [rcx+10h], r15
0x18009e14c  mov     r8d, esi
0x18009e14f  mov     [rcx+18h], r15
0x18009e153  mov     rdx, rdi
0x18009e156  mov     rcx, cs:PublisherHandle
0x18009e15d  mov     [rsp+178h+var_158], r15d
0x18009e162  call    cs:__imp_EtwEventWrite
0x18009e168  mov     rcx, [rsp+178h+var_38]
0x18009e170  xor     rcx, rsp; StackCookie
0x18009e173  call    __security_check_cookie
0x18009e178  lea     r11, [rsp+178h+var_28]
0x18009e180  mov     rbx, [r11+30h]
0x18009e184  mov     rbp, [r11+48h]
0x18009e188  mov     rsp, r11
0x18009e18b  pop     r15
0x18009e18d  pop     r14
0x18009e18f  pop     r12
0x18009e191  pop     rdi
0x18009e192  pop     rsi
0x18009e193  retn
```
