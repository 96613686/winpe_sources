# NfsRdrpInitAutomountDfsMaps

- ea: `0x14002e8e4`
- end: `0x14002eb11`
- name: `NfsRdrpInitAutomountDfsMaps`
- size: `557`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x14002d428`

## callees

- `0x14002e8e4`
- `0x140038550`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14002ea99`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002eaad`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002ea99`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002eaad`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14002eaf3`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14002eaf3`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002e9ce`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002e9ce`
- `ntoskrnl!ExAllocatePool2` at `0x14002ea48`
- `ntoskrnl!ExAllocatePool2` at `0x14002ea48`

## string_xrefs

- `0x14002e915`: `MountSymlinkDfsMaps`

## pseudocode

```c
void __fastcall NfsRdrpInitAutomountDfsMaps(__int64 a1)
{
  PWSTR Buffer; // rsi
  WCHAR v3; // cx
  const WCHAR *v4; // rdx
  WCHAR v5; // ax
  unsigned __int64 i; // rax
  USHORT v7; // ax
  unsigned __int64 v8; // rcx
  USHORT v9; // cx
  __int64 Pool2; // rdi
  unsigned __int16 v11; // dx
  __int64 v12; // rax
  UNICODE_STRING SourceString; // [rsp+30h] [rbp-38h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-28h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+50h] [rbp-18h] BYREF

  *(_QWORD *)(a1 + 2008) = 0;
  *(_QWORD *)&UnicodeString.Length = 0;
  UnicodeString.Buffer = 0;
  NfsReadRegistry(
    &stru_140041080,
    L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Defaults",
    (__int64)&UnicodeString,
    16);
  Buffer = UnicodeString.Buffer;
  if ( UnicodeString.Buffer )
  {
    SourceString = 0;
    DestinationString = 0;
    if ( *UnicodeString.Buffer )
    {
      do
      {
        v3 = *Buffer;
        if ( *Buffer == 47 )
        {
          do
            ++Buffer;
          while ( *Buffer == 47 );
          v3 = *Buffer;
        }
        v4 = Buffer;
        if ( v3 )
        {
          do
          {
            if ( *v4 == 58 )
              break;
            ++v4;
          }
          while ( *v4 );
        }
        SourceString.Buffer = Buffer;
        SourceString.MaximumLength = (_WORD)v4 - (_WORD)Buffer;
        SourceString.Length = (_WORD)v4 - (_WORD)Buffer;
        v5 = *v4;
        if ( *v4 == 58 )
          v5 = *++v4;
        if ( v5 == 92 )
        {
          do
            ++v4;
          while ( *v4 == 92 );
        }
        RtlInitUnicodeString(&DestinationString, v4);
        for ( i = (unsigned __int64)SourceString.Length >> 1; i; --i )
        {
          if ( SourceString.Buffer[i - 1] != 47 )
            break;
        }
        v7 = 2 * i;
        v8 = (unsigned __int64)DestinationString.Length >> 1;
        for ( SourceString.Length = v7; v8; --v8 )
        {
          if ( DestinationString.Buffer[v8 - 1] != 92 )
            break;
        }
        v9 = 2 * v8;
        DestinationString.Length = v9;
        if ( v7 && v9 )
        {
          Pool2 = ExAllocatePool2(258, v9 + 44LL + v7, 1095919182);
          *(_WORD *)(Pool2 + 8) = 0;
          *(_QWORD *)(Pool2 + 16) = Pool2 + 40;
          v11 = SourceString.Length + 2;
          *(_WORD *)(Pool2 + 24) = 0;
          *(_WORD *)(Pool2 + 10) = v11;
          *(_QWORD *)(Pool2 + 32) = Pool2 + v11 + 40LL;
          *(_WORD *)(Pool2 + 26) = DestinationString.Length + 2;
          RtlCopyUnicodeString((PUNICODE_STRING)(Pool2 + 8), &SourceString);
          RtlCopyUnicodeString((PUNICODE_STRING)(Pool2 + 24), &DestinationString);
          *(_QWORD *)Pool2 = *(_QWORD *)(a1 + 2008);
          *(_QWORD *)(a1 + 2008) = Pool2;
        }
        v12 = -1;
        do
          ++v12;
        while ( Buffer[v12] );
        Buffer += v12 + 1;
      }
      while ( *Buffer );
    }
    RtlFreeUnicodeString(&UnicodeString);
  }
}

```

## disassembly

```asm
0x14002e8e4  push    rbp
0x14002e8e6  push    rbx
0x14002e8e7  push    rsi
0x14002e8e8  push    rdi
0x14002e8e9  push    r12
0x14002e8eb  push    r13
0x14002e8ed  push    r14
0x14002e8ef  push    r15
0x14002e8f1  mov     rbp, rsp
0x14002e8f4  sub     rsp, 68h
0x14002e8f8  xor     r15d, r15d
0x14002e8fb  mov     [rsp+68h+var_40], 10h; int
0x14002e903  mov     r14, rcx
0x14002e906  mov     [rcx+7D8h], r15
0x14002e90d  lea     rax, [rbp+UnicodeString]
0x14002e911  mov     qword ptr [rbp+UnicodeString.Length], r15
0x14002e915  lea     r8, aMountsymlinkdf; "MountSymlinkDfsMaps"
0x14002e91c  mov     [rbp+UnicodeString.Buffer], r15
0x14002e920  lea     r9d, [r15+7]
0x14002e924  mov     [rsp+68h+var_48], rax; __int64
0x14002e929  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x14002e930  lea     rcx, stru_140041080; SourceString
0x14002e937  call    NfsReadRegistry
0x14002e93c  mov     rsi, [rbp+UnicodeString.Buffer]
0x14002e940  test    rsi, rsi
0x14002e943  jz      loc_14002EAFF
0x14002e949  xorps   xmm0, xmm0
0x14002e94c  xorps   xmm1, xmm1
0x14002e94f  movups  xmmword ptr [rbp+SourceString.Length], xmm0
0x14002e953  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x14002e957  cmp     r15w, [rsi]
0x14002e95b  jz      loc_14002EAEF
0x14002e961  lea     r8d, [r15+3Ah]
0x14002e965  lea     r12d, [r15+2]
0x14002e969  lea     r13d, [r15+5Ch]
0x14002e96d  movzx   ecx, word ptr [rsi]
0x14002e970  cmp     cx, 2Fh ; '/'
0x14002e974  jnz     short loc_14002E982
0x14002e976  add     rsi, r12
0x14002e979  cmp     word ptr [rsi], 2Fh ; '/'
0x14002e97d  jz      short loc_14002E976
0x14002e97f  movzx   ecx, word ptr [rsi]
0x14002e982  mov     rdx, rsi
0x14002e985  cmp     r15w, cx
0x14002e989  jz      short loc_14002E99A
0x14002e98b  cmp     [rdx], r8w
0x14002e98f  jz      short loc_14002E99A
0x14002e991  add     rdx, r12
0x14002e994  cmp     r15w, [rdx]
0x14002e998  jnz     short loc_14002E98B
0x14002e99a  movzx   eax, dx
0x14002e99d  mov     [rbp+SourceString.Buffer], rsi
0x14002e9a1  sub     ax, si
0x14002e9a4  mov     [rbp+SourceString.MaximumLength], ax
0x14002e9a8  mov     [rbp+SourceString.Length], ax
0x14002e9ac  movzx   eax, word ptr [rdx]
0x14002e9af  cmp     r8w, ax
0x14002e9b3  jnz     short loc_14002E9BB
0x14002e9b5  add     rdx, r12
0x14002e9b8  movzx   eax, word ptr [rdx]
0x14002e9bb  cmp     r13w, ax
0x14002e9bf  jnz     short loc_14002E9CA
0x14002e9c1  add     rdx, r12; SourceString
0x14002e9c4  cmp     r13w, [rdx]
0x14002e9c8  jz      short loc_14002E9C1
0x14002e9ca  lea     rcx, [rbp+DestinationString]; DestinationString
0x14002e9ce  call    cs:__imp_RtlInitUnicodeString
0x14002e9d5  nop     dword ptr [rax+rax+00h]
0x14002e9da  movzx   eax, [rbp+SourceString.Length]
0x14002e9de  shr     rax, 1
0x14002e9e1  jz      short loc_14002E9F5
0x14002e9e3  mov     rcx, [rbp+SourceString.Buffer]
0x14002e9e7  cmp     word ptr [rcx+rax*2-2], 2Fh ; '/'
0x14002e9ed  jnz     short loc_14002E9F5
0x14002e9ef  sub     rax, 1
0x14002e9f3  jnz     short loc_14002E9E7
0x14002e9f5  movzx   ecx, [rbp+DestinationString.Length]
0x14002e9f9  add     ax, ax
0x14002e9fc  shr     rcx, 1
0x14002e9ff  mov     [rbp+SourceString.Length], ax
0x14002ea03  jz      short loc_14002EA17
0x14002ea05  mov     rdx, [rbp+DestinationString.Buffer]
0x14002ea09  cmp     [rdx+rcx*2-2], r13w
0x14002ea0f  jnz     short loc_14002EA17
0x14002ea11  sub     rcx, 1
0x14002ea15  jnz     short loc_14002EA09
0x14002ea17  add     cx, cx
0x14002ea1a  mov     [rbp+DestinationString.Length], cx
0x14002ea1e  test    ax, ax
0x14002ea21  jz      loc_14002EACA
0x14002ea27  test    cx, cx
0x14002ea2a  jz      loc_14002EACA
0x14002ea30  movzx   ecx, cx
0x14002ea33  mov     r8d, 4152664Eh
0x14002ea39  add     rcx, 2Ch ; ','
0x14002ea3d  movzx   edx, ax
0x14002ea40  add     rdx, rcx
0x14002ea43  mov     ecx, 102h
0x14002ea48  call    cs:__imp_ExAllocatePool2
0x14002ea4f  nop     dword ptr [rax+rax+00h]
0x14002ea54  mov     rdi, rax
0x14002ea57  lea     rcx, [rax+28h]
0x14002ea5b  mov     [rax+8], r15w
0x14002ea60  mov     [rax+10h], rcx
0x14002ea64  lea     rcx, [rdi+8]; DestinationString
0x14002ea68  movzx   edx, [rbp+SourceString.Length]
0x14002ea6c  add     dx, r12w
0x14002ea70  mov     [rax+18h], r15w
0x14002ea75  movzx   r8d, dx
0x14002ea79  mov     [rax+0Ah], r8w
0x14002ea7e  lea     rdx, [r8+28h]
0x14002ea82  add     rdx, rax
0x14002ea85  mov     [rax+20h], rdx
0x14002ea89  lea     rdx, [rbp+SourceString]; SourceString
0x14002ea8d  movzx   eax, [rbp+DestinationString.Length]
0x14002ea91  add     ax, r12w
0x14002ea95  mov     [rdi+1Ah], ax
0x14002ea99  call    cs:__imp_RtlCopyUnicodeString
0x14002eaa0  nop     dword ptr [rax+rax+00h]
0x14002eaa5  lea     rdx, [rbp+DestinationString]; SourceString
0x14002eaa9  lea     rcx, [rdi+18h]; DestinationString
0x14002eaad  call    cs:__imp_RtlCopyUnicodeString
0x14002eab4  nop     dword ptr [rax+rax+00h]
0x14002eab9  mov     rax, [r14+7D8h]
0x14002eac0  mov     [rdi], rax
0x14002eac3  mov     [r14+7D8h], rdi
0x14002eaca  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002eace  inc     rax
0x14002ead1  cmp     [rsi+rax*2], r15w
0x14002ead6  jnz     short loc_14002EACE
0x14002ead8  lea     rsi, [rsi+rax*2]
0x14002eadc  mov     r8d, 3Ah ; ':'
0x14002eae2  add     rsi, r12
0x14002eae5  cmp     r15w, [rsi]
0x14002eae9  jnz     loc_14002E96D
0x14002eaef  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14002eaf3  call    cs:__imp_RtlFreeUnicodeString
0x14002eafa  nop     dword ptr [rax+rax+00h]
0x14002eaff  add     rsp, 68h
0x14002eb03  pop     r15
0x14002eb05  pop     r14
0x14002eb07  pop     r13
0x14002eb09  pop     r12
0x14002eb0b  pop     rdi
0x14002eb0c  pop     rsi
0x14002eb0d  pop     rbx
0x14002eb0e  pop     rbp
0x14002eb0f  retn
```
