# IISCompressionEvents::STATIC_COMPRESSION_NOT_SUCCESS::TranslateEnumReasonToString(IISCompressionEvents::STATIC_COMPRESSION_NOT_SUCCESS::enumReason)

- ea: `0x180008ab0`
- end: `0x180008b49`
- name: `?TranslateEnumReasonToString@STATIC_COMPRESSION_NOT_SUCCESS@IISCompressionEvents@@SAPEBGW4enumReason@12@@Z`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008624`

## callees

- `0x180008ab0`

## string_xrefs

- `0x180008ad6`: `COMPRESSION_DISABLED`
- `0x180008ade`: `NO_COMPRESSION_10`
- `0x180008ae6`: `NO_COMPRESSION_PROXY`
- `0x180008afe`: `NO_COMPRESSION_RANGE`
- `0x180008b16`: `COMPRESS_FILE_NOT_FOUND`
- `0x180008b1e`: `COMPRESS_FILE_STALE`
- `0x180008b3e`: `FAIL_TO_COMPRESS`

## pseudocode

```c
const wchar_t *__fastcall IISCompressionEvents::STATIC_COMPRESSION_NOT_SUCCESS::TranslateEnumReasonToString(int a1)
{
  const wchar_t *result; // rax

  switch ( a1 )
  {
    case 1:
      result = L"NO_ACCEPT_ENCODING";
      break;
    case 2:
      result = L"COMPRESSION_DISABLED";
      break;
    case 3:
      result = L"NO_COMPRESSION_10";
      break;
    case 4:
      result = L"NO_COMPRESSION_PROXY";
      break;
    case 5:
      result = L"NO_MATCHING_SCHEME";
      break;
    case 6:
      result = L"UNKNOWN_ERROR";
      break;
    case 7:
      result = L"NO_COMPRESSION_RANGE";
      break;
    case 8:
      result = L"FILE_TOO_SMALL";
      break;
    case 9:
      result = L"FILE_ENCRYPTED";
      break;
    case 10:
      result = L"COMPRESS_FILE_NOT_FOUND";
      break;
    case 11:
      result = L"COMPRESS_FILE_STALE";
      break;
    case 12:
      result = L"NO_MATCHING_CONTENT_TYPE";
      break;
    case 13:
      result = L"FOOTER_ENABLED";
      break;
    case 14:
      result = L"NOT_FREQUENTLY_HIT";
      break;
    case 15:
      result = L"FAIL_TO_COMPRESS";
      break;
    default:
      result = 0;
      break;
  }
  return result;
}

```

## disassembly

```asm
0x180008ab0  dec     ecx; switch 15 cases
0x180008ab2  cmp     ecx, 0Eh
0x180008ab5  ja      def_180008ACC; jumptable 0000000180008ACC default case
0x180008abb  lea     rdx, cs:180000000h
0x180008ac2  mov     eax, ds:(jpt_180008ACC - 180000000h)[rdx+rcx*4]
0x180008ac9  add     rax, rdx
0x180008acc  jmp     rax; switch jump
0x180008ace  lea     rax, aNoAcceptEncodi; jumptable 0000000180008ACC case 1
0x180008ad5  retn
0x180008ad6  lea     rax, aCompressionDis; jumptable 0000000180008ACC case 2
0x180008add  retn
0x180008ade  lea     rax, aNoCompression1; jumptable 0000000180008ACC case 3
0x180008ae5  retn
0x180008ae6  lea     rax, aNoCompressionP; jumptable 0000000180008ACC case 4
0x180008aed  retn
0x180008aee  lea     rax, aNoMatchingSche; jumptable 0000000180008ACC case 5
0x180008af5  retn
0x180008af6  lea     rax, aUnknownError; jumptable 0000000180008ACC case 6
0x180008afd  retn
0x180008afe  lea     rax, aNoCompressionR; jumptable 0000000180008ACC case 7
0x180008b05  retn
0x180008b06  lea     rax, aFileTooSmall; jumptable 0000000180008ACC case 8
0x180008b0d  retn
0x180008b0e  lea     rax, aFileEncrypted; jumptable 0000000180008ACC case 9
0x180008b15  retn
0x180008b16  lea     rax, aCompressFileNo; jumptable 0000000180008ACC case 10
0x180008b1d  retn
0x180008b1e  lea     rax, aCompressFileSt; jumptable 0000000180008ACC case 11
0x180008b25  retn
0x180008b26  lea     rax, aNoMatchingCont; jumptable 0000000180008ACC case 12
0x180008b2d  retn
0x180008b2e  lea     rax, aFooterEnabled; jumptable 0000000180008ACC case 13
0x180008b35  retn
0x180008b36  lea     rax, aNotFrequentlyH; jumptable 0000000180008ACC case 14
0x180008b3d  retn
0x180008b3e  lea     rax, aFailToCompress; jumptable 0000000180008ACC case 15
0x180008b45  retn
0x180008b46  xor     eax, eax; jumptable 0000000180008ACC default case
0x180008b48  retn
```
